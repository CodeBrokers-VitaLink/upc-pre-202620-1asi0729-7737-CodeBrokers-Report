## 4.6. Domain-Driven Software Architecture

El diseño de VitaLink se organiza en cuatro Bounded Contexts: Monitoring, Emergency & Notification, IAM & Profile y Triage & Scheduling. Los tres primeros sustentan las historias del piloto; Triage & Scheduling representa una evolución futura, fuera de las 37 historias del backlog actual. Estos límites son los mismos en el Big Picture, el Design-Level Event Storming, el modelo táctico de 4.7 y los diagramas C4 de esta sección.

Los diagramas especifican el diseño objetivo del backend en Java y Spring Boot. En TB1 se demuestra el frontend con una fake API; el diseño no acredita implementación de seguridad, envío de SMS ni integración con agendas clínicas. Esos adaptadores deben comprobarse en el hito de implementación que corresponda.

### 4.6.1. Design-Level Event Storming

Se refinan los conceptos del Big Picture de [2.4](../20-chapter-two/24-big-picture-eventstorming.md) distinguiendo comandos, Aggregate Roots, objetos internos, eventos, políticas y consultas. La raíz es el límite de consistencia: BiometricRecord, CaregiverAffiliation y MedicalAppointmentReservation son entidades internas; NotificationChannel es un Value Object, no un aggregate con envío propio.

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.80\textheight,keepaspectratio]{assets/event-brainstorming.png}
\caption{Design-Level Event Storming: límites contextuales y eventos de integración}
\end{figure}

| Bounded Context | Aggregate Roots | Entidades internas | Value Objects principales |
|---|---|---|---|
| Monitoring | VitalSignsTracker | BiometricRecord | BiometricReading, Baseline |
| Emergency & Notification | EmergencyAlert | AlertObservation | ObservedValue, NotificationChannel |
| IAM & Profile | UserAccount, PatientProfile | CaregiverAffiliation | ProviderAffiliation |
| Triage & Scheduling, futuro | TriageAssessment | MedicalAppointmentReservation | TimeSlot |

NotificationChannel es un valor seleccionado por la política de notificación y queda fuera del aggregate EmergencyAlert. El adaptador de envío tampoco forma parte de ese aggregate.

#### 4.6.1.1. Monitoring Bounded Context

- **Propósito:** registrar lecturas de dispositivos o de modo asistido, evaluarlas contra la línea base y consultar su historial.
- **Aggregate Root:** VitalSignsTracker, identificado por patientId; contiene BiometricRecord, BiometricReading y Baseline.
- **Comandos:** RecordVitalSigns y UpdateBaseline.
- **Domain Events:** VitalSignsRecorded y ThresholdExceeded.
- **Consultas:** GetLatestVitalSignsQuery y GetBiometricHistoryQuery, sobre modelos de lectura; no requieren cargar el historial completo en el aggregate.
- **Invariantes:** pertenencia al paciente, línea base del tipo de lectura, origen obligatorio y emisión de ThresholdExceeded al aceptar una desviación. Se detallan como M-01 a M-04 en 4.7.

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.80\textheight,keepaspectratio]{assets/Monitoring_BC.png}
\caption{Monitoring: comandos, raíz, eventos y consultas}
\end{figure}

La detección de patrones de caída y el procesamiento continuo del simulador son hipótesis de evolución del Big Picture. No se presentan como comportamiento ya implementado ni como eventos emitidos por el modelo táctico del piloto.

#### 4.6.1.2. Emergency & Notification Bounded Context

- **Propósito:** mantener el ciclo de vida de alertas y coordinar los avisos a la red de apoyo.
- **Aggregate Root:** EmergencyAlert; contiene AlertObservation y, cuando la causa es biométrica, ObservedValue.
- **Comandos:** TriggerEmergencyAlert, RequestHelp, StartReview, MarkAttended y AddObservation.
- **Domain Events:** EmergencyAlertTriggered y AlertStatusChanged.
- **Integración de entrada:** un handler traduce ThresholdExceeded y crea la alerta; el aggregate no importa ni modifica VitalSignsTracker.
- **Consultas:** GetActiveAlertsQuery y GetAlertAuditTrailQuery.
- **Notificación:** RoleBasedNotificationPolicy selecciona destinatario/canal sin I/O; un handler de aplicación invoca el puerto de envío. NotificationChannel es un VO sin identidad ni método dispatch().

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.80\textheight,keepaspectratio]{assets/E&N_BC.png}
\caption{Emergency \& Notification: ciclo de alerta y política de notificación}
\end{figure}

#### 4.6.1.3. Triage & Scheduling Bounded Context, evolución futura

- **Propósito propuesto:** evaluar el riesgo y coordinar propuestas y confirmaciones de citas.
- **Aggregate Root:** TriageAssessment, asociado por alertId; MedicalAppointmentReservation es una entidad interna y TimeSlot es un VO.
- **Comandos previstos:** EvaluateClinicalRisk, PreScheduleAppointment y ConfirmAppointment.
- **Domain Events previstos:** RiskEvaluated, AppointmentPreScheduled y AppointmentConfirmed.
- **Integración futura:** EmergencyAlertTriggered inicia la evaluación. SchedulingPolicy decide sobre disponibilidad suministrada por un adaptador; consultar una agenda externa no es una invariante interna.
- **Consultas previstas:** SearchAvailableMedicalSlotsQuery y ExportTriageSummaryQuery.

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.80\textheight,keepaspectratio]{assets/T&C_Scheduling_BC.png}
\caption{Triage \& Scheduling: diseño futuro, fuera del alcance del piloto}
\end{figure}

#### 4.6.1.4. IAM & Profile Bounded Context

- **Propósito:** identidad, roles, afiliación del paciente a un proveedor y red de cuidado.
- **Aggregate Roots:** UserAccount y PatientProfile. CaregiverAffiliation pertenece a PatientProfile; no es una raíz independiente.
- **Comandos:** RegisterUser, LinkCaregiverToPatient, UpdateCaregiverContact, AssignProvider y ActivateMonitoring.
- **Domain Events:** UserRegistered y CaregiverNetworkUpdated.
- **Consultas:** GetUserProfileQuery y GetAffiliatedPatientsQuery.
- **Acceso:** la aplicación verifica identidad, rol y afiliación antes de ejecutar una operación; JWT y sus filtros son mecanismos del adaptador de seguridad, no comportamiento de un VO o entidad.

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.80\textheight,keepaspectratio]{assets/IAM_BC.png}
\caption{IAM \& Profile: raíces independientes, afiliaciones y acceso por identificador}
\end{figure}

#### 4.6.1.5. Fronteras y contratos de integración

Cada transacción modifica una raíz y sus objetos internos. Los demás aggregates se referencian por identificador. Al cruzar un Bounded Context, los eventos de dominio se traducen a contratos de integración con IDs, valores y fecha del suceso; no se comparten entidades ni Value Objects del dominio emisor.

| Origen | Contrato / consulta | Destino | Responsabilidad |
|---|---|---|---|
| Monitoring | ThresholdExceeded | Emergency & Notification | Crear la alerta a partir de la lectura y el rango observados |
| IAM & Profile | Consulta por patientId/userId | Monitoring y Emergency & Notification | Resolver afiliación, autorización y destinatarios |
| Emergency & Notification | EmergencyAlertTriggered / AlertStatusChanged | Handler de notificación del mismo contexto | Seleccionar canal y ejecutar el adaptador |
| Emergency & Notification | EmergencyAlertTriggered, futuro | Triage & Scheduling | Iniciar evaluación y coordinación de cita |

La emisión del evento forma parte de la transición del aggregate. La entrega a consumidores es una responsabilidad distinta de aplicación e infraestructura. Un bus en memoria no garantiza entrega tras una caída; la persistencia, los reintentos y la idempotencia deben resolverse y verificarse cuando se implemente el backend. El diseño no afirma que la fake API entregue estos eventos.

### 4.6.2. Software Architecture Context Diagram

El nivel 1 de C4 muestra un sistema VitaLink y sus usuarios: familiares, adultos mayores y profesionales de salud. El simulador de dispositivos, el proveedor de notificaciones y la agenda clínica son sistemas externos; estos dos últimos son integraciones propuestas o futuras.

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.80\textheight,keepaspectratio]{assets/Software_Architecture_Context_Diagram.png}
\caption{C4 nivel 1: sistema, usuarios e integraciones externas}
\end{figure}

### 4.6.3. Software Architecture Container Diagram

El nivel 2 distingue unidades de despliegue del diseño objetivo: WebApp Angular/TypeScript, Backend API Java/Spring Boot y base de datos MySQL. Los cuatro Bounded Contexts son módulos internos del Backend API, no Software Systems adicionales ni contenedores desplegados por separado. Ambos segmentos usan vistas de la misma WebApp.

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.80\textheight,keepaspectratio]{assets/Software_Architecture_Container_Diagram.png}
\caption{C4 nivel 2: contenedores del diseño objetivo de VitaLink}
\end{figure}

La fake API de TB1 sustituye temporalmente al backend para la demostración del frontend. El diagrama describe la arquitectura objetivo; no presenta la base MySQL o los adaptadores externos como desplegados en TB1.

### 4.6.4. Software Architecture Component Diagram

El nivel 3 descompone el Backend API propuesto en los componentes IAM & Profile, Monitoring y Emergency & Notification, con Triage & Scheduling identificado como futuro. El historial clínico es un modelo de lectura de Monitoring, no un quinto Bounded Context.

Los controladores y handlers de aplicación coordinan operaciones; los aggregates protegen invariantes; los adaptadores Spring Data JPA implementan persistencia. Los puertos de notificación y agenda mantienen los efectos externos fuera del dominio. La autorización se aplica en servidor antes de atender consultas u operaciones.

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.80\textheight,keepaspectratio]{assets/Software_Architecture_Component_Diagram.png}
\caption{C4 nivel 3: componentes internos y adaptadores del backend propuesto}
\end{figure}

La WebApp consume JSON/HTTPS; la persistencia objetivo usa Spring Data JPA/Hibernate sobre JDBC/TCP. Los vínculos de eventos entre componentes no representan llamadas directas a entidades de otro contexto.

Los fuentes Mermaid y sus SVG se incluyen en [8.1](../80-annexes/81-annexes.md). Las invariantes, estereotipos, multiplicidades y trazabilidad a historias se detallan en [4.7](47-software-object-oriented-design.md).
