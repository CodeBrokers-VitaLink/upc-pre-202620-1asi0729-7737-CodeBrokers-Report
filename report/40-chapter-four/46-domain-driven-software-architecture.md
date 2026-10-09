## 4.6. Domain-Driven Software Architecture

En esta seccion se formaliza la arquitectura de software de VitaLink bajo los principios de Domain-Driven Design (DDD) y el modelo C4. Se descompone la complejidad del dominio de telemonitoreo geriatrico en limites contextuales claros y se estructuran los niveles de abstraccion del sistema (Contexto, Contenedores y Componentes) para garantizar escalabilidad, mantenibilidad y alta disponibilidad ante incidentes criticos.

Los diagramas C4 de esta seccion distinguen explicitamente dos estados. Los elementos **implementados y desplegados** corresponden al front-end Angular que hoy opera sobre una API simulada, organizado en los contextos delimitados `care` e `iam`. Los elementos **planificados para TB2** corresponden al backend y a los servicios externos que completan la visión del producto y que todavía no se encuentran desplegados; se mantienen en los diagramas porque la evolución del sistema está prevista sobre ellos. Esta convención evita que el lector confunda el diseño objetivo con lo que efectivamente está en operación.

### 4.6.1. Design-Level Event Storming

A partir del Big Picture preliminar, se desarrollo la sesion de Design-Level Event Storming para refinar el modelo del dominio. Se definieron cuatro Bounded Contexts principales con sus respectivos comandos, eventos de dominio, agregados y modelos de lectura (queries):

\begin{center} \includegraphics[width=\linewidth]{assets/event-brainstorming.png} \end{center}

#### 1. Monitoring Bounded Context
* **Proposito:** Administrar la telemetria fisiologica en tiempo real, evaluando lecturas frente a rangos clinicos predefinidos.
* **Aggregates:** `BiometricRecord`, `VitalSignsTracker`.
* **Commands:** `RecordVitalSigns`, `ProcessTelemetryStream`, `VerifyThresholds`.
* **Domain Events:** `VitalSignsRecorded`, `ThresholdExceeded`, `FallPatternDetected`.
* **Read Models (Queries):** `GetLatestVitalSignsQuery`, `GetBiometricHistoryQuery`.

\begin{center} \includegraphics[width=\linewidth]{assets/Monitoring_BC.png} \end{center}

#### 2. Emergency & Notification Bounded Context
* **Proposito:** Orquestar el despacho de alertas de emergencia y controlar el escalamiento multicanal hacia la red de apoyo familiar.
* **Aggregates:** `EmergencyAlert`, `NotificationChannel`.
* **Commands:** `TriggerEmergencyAlert`, `AcknowledgeAlert`, `EscalateNotification`.
* **Domain Events:** `EmergencyAlertTriggered`, `AlertAcknowledgedByCaregiver`, `AlertEscalated`.
* **Read Models (Queries):** `GetActiveAlertsQuery`, `GetAlertAuditTrailQuery`.

\begin{center} \includegraphics[width=\linewidth]{assets/E&N_BC.png} \end{center}

#### 3. Triage & Clinical Scheduling Bounded Context
* **Proposito:** Clasificar el nivel de gravedad clinica del paciente y pre-agendar de manera reactiva citas en la red de centros de salud aliados.
* **Aggregates:** `TriageAssessment`, `MedicalAppointmentReservation`.
* **Commands:** `EvaluateClinicalRisk`, `PreScheduleAppointment`, `ConfirmAppointment`.
* **Domain Events:** `RiskEvaluated`, `AppointmentPreScheduled`, `AppointmentConfirmed`.
* **Read Models (Queries):** `SearchAvailableMedicalSlotsQuery`, `ExportTriageSummaryQuery`.

\begin{center} \includegraphics[width=\linewidth]{assets/T&C_Scheduling_BC.png} \end{center}

#### 4. IAM & Profile Bounded Context
* **Proposito:** Gestionar la identidad, control de accesos, roles y vinculaciones familiares entre el paciente y sus tutores legales.
* **Aggregates:** `UserAccount`, `CaregiverAffiliation`.
* **Commands:** `RegisterUser`, `AuthenticateUser`, `LinkCaregiverToPatient`.
* **Domain Events:** `UserRegistered`, `UserAuthenticated`, `CaregiverLinked`.
* **Read Models (Queries):** `GetUserProfileQuery`, `GetAffiliatedPatientsQuery`.

\begin{center} \includegraphics[width=\linewidth]{assets/IAM_BC.png} \end{center}

### 4.6.2. Software Architecture Context Diagram

El diagrama de contexto representa el Nivel 1 del modelo C4 para VitaLink Platform. Delimita las fronteras del sistema y muestra como un unico recuadro central a la plataforma, rodeada por los usuarios que interactuan con ella y por los sistemas externos con los que se integrara.

\begin{center} \includegraphics[width=\linewidth]{assets/diagrams/c4-01-context.png} \end{center}

#### 1. Elemento Central

* **VitaLink Platform [Software System]:** Telemonitoreo geriatrico. Registra pacientes, lee signos vitales, gestiona alertas de salud y coordina la red de cuidado familiar y profesional. Se encuentra implementado y desplegado.

#### 2. Usuarios (Person)

* **Cuidador Familiar [Person]:** Monitorea y atiende las alertas del adulto mayor a su cargo. Implementado.
* **Personal Medico [Person]:** Supervisa los pacientes que tiene asignados y gestiona sus alertas. Implementado.
* **Adulto Mayor [Person]:** Paciente monitoreado en domicilio. Su acceso de consulta esta previsto para una etapa posterior, por lo que se representa como planificado.

#### 3. Sistemas Externos (External Software Systems)

Los tres sistemas externos se representan como planificados para TB2, porque la integracion todavia no esta desplegada:

* **Pasarela SMS [Software System]:** Envio de alertas criticas a la red de apoyo familiar cuando el cuidador no confirma la recepcion.
* **Agenda Clinica Externa [Software System]:** Disponibilidad y reserva de citas medicas ambulatorias y de urgencia.
* **Simulador IoT [Software System]:** Emision continua de telemetria fisiologica y deteccion de caidas en el domicilio.

#### 4. Relaciones y Protocolos de Comunicacion

* **Cuidador Familiar -> VitaLink Platform:** Consulta el tablero, la red familiar y el detalle de alertas mediante `HTTPS`.
* **Personal Medico -> VitaLink Platform:** Revisa los pacientes asignados y registra intervenciones sobre alertas mediante `HTTPS`.
* **VitaLink Platform -> Pasarela SMS:** Despacha alertas de emergencia mediante servicios web `REST/HTTPS`. Planificado.
* **VitaLink Platform -> Agenda Clinica Externa:** Pre-agenda consultas de urgencia mediante `REST/HTTPS`. Planificado.
* **Simulador IoT -> VitaLink Platform:** Envia telemetria biometrica empaquetada en formato estructurado mediante `JSON/HTTPS`. Planificado.
* **Adulto Mayor -> VitaLink Platform:** Emite solicitud de auxilio mediante `HTTPS`. Planificado.

### 4.6.3. Software Architecture Container Diagrams

El diagrama de contenedores describe el Nivel 2 del modelo C4 y detalla las unidades de despliegue que componen VitaLink Platform. Se presenta un unico diagrama porque una sola aplicacion web atiende a ambos roles: la vista que ve el cuidador familiar y la que ve el personal medico se resuelven dentro del mismo contenedor, en funcion del rol de la sesion.

\begin{center} \includegraphics[width=\linewidth]{assets/diagrams/c4-02-container.png} \end{center}

#### 1. Contenedores Implementados

* **VitaLink WebApp [Container: Angular 22, TypeScript, Angular Material]:** Aplicacion de pagina unica que renderiza el inicio de sesion, el perfil, el tablero de pacientes, el detalle de alertas y la red familiar. Organiza su codigo en los contextos delimitados `care` e `iam`.
* **API simulada [Container: JSON Server 0.17 sobre Node.js]:** Capa de datos de demostracion desplegada en Render. Expone las colecciones `patients`, `alerts`, `records`, `interventions`, `caregivers`, `measurementRanges` y `users` mediante servicios REST. Ocupa el lugar del backend mientras este no exista.
* **Almacenamiento de sesion [Container: sessionStorage]:** Conserva el identificador de usuario y su rol mientras la pestana permanece abierta. No almacena credenciales.

#### 2. Contenedores Planificados para TB2

* **Backend API [Container: Java 21, Spring Boot, Spring Data JPA]:** Reemplazara la API simulada y concentrara las reglas de negocio que hoy se resuelven en el cliente, ademas de la autenticacion con tokens.
* **Base de datos [Container: MySQL]:** Persistencia relacional del dominio: pacientes, registros, alertas, intervenciones, cuidadores y usuarios.

#### 3. Relaciones y Protocolos de Comunicacion

* **Cuidador Familiar / Personal Medico -> VitaLink WebApp:** Uso de la aplicacion web mediante `HTTPS`.
* **VitaLink WebApp -> API simulada:** Consulta y actualizacion del dominio mediante `JSON/HTTPS`.
* **VitaLink WebApp -> Almacenamiento de sesion:** Guarda y restaura la sesion mediante `Web Storage API`.
* **VitaLink WebApp -> Backend API:** Consumira los servicios REST del backend mediante `JSON/HTTPS`. Planificado.
* **Backend API -> Base de datos:** Lectura y persistencia del dominio mediante `JDBC / JPA`. Planificado.
* **Simulador IoT -> Backend API:** Envio de telemetria biometrica mediante `JSON/HTTPS`. Planificado.
* **Backend API -> Pasarela SMS:** Despacho de alertas de emergencia mediante `REST/HTTPS`. Planificado.
* **Backend API -> Agenda Clinica Externa:** Pre-agendamiento de consultas de urgencia mediante `REST/HTTPS`. Planificado.

### 4.6.4. Software Architecture Component Diagrams

El diagrama de componentes representa el Nivel 3 del modelo C4. Se elabora un diagrama por contenedor y, en el caso del contenedor implementado, uno por cada contexto delimitado, porque la aplicacion web agrupa un numero de componentes que en una sola figura resultaba ilegible. Los dos primeros diagramas describen el contenedor VitaLink WebApp; el tercero describe el contenedor Backend API planificado.

#### 1. Componentes del contexto IAM

\begin{center} \includegraphics[width=\linewidth]{assets/diagrams/c4-03-components-iam.png} \end{center}

Agrupa los componentes que resuelven la identidad y el control de acceso:

* **Login [Vista]:** Formulario que inicia la sesion.
* **Profile [Vista]:** Muestra los datos del usuario autenticado y permite cerrar sesion.
* **roleGuard [Guard]:** Restringe cada ruta al rol declarado y redirige al inicio del rol cuando no coincide.
* **AuthenticationStore [Store]:** Mantiene la sesion activa y expone el rol del usuario al resto de la aplicacion.
* **UserStore [Store]:** Carga el perfil del usuario autenticado por su identificador.
* **AuthenticationService [HttpClient]:** Valida las credenciales contra la API y persiste o restaura la sesion.
* **UserService [HttpClient]:** Obtiene el perfil del usuario desde la API.
* **Contexto compartido:** `LocalizedDateService` y `LanguageSwitcher`, reutilizados por ambas vistas.

#### 2. Componentes del contexto Care

\begin{center} \includegraphics[width=0.70\linewidth]{assets/diagrams/c4-04-components-care.png} \end{center}

Agrupa los componentes del seguimiento del paciente. El modelo de dominio y el servicio de dominio se destacan en verde porque concentran las reglas del negocio:

* **CareWorkspace [Vista]:** Tablero unico que adapta su contenido al rol y a la vista solicitada: panel, pacientes, detalle de alerta y red familiar.
* **AlertList [Componente]:** Lista las alertas de un paciente ordenadas por severidad y permite cambiar su estado.
* **PatientSummary [Componente]:** Resume la ficha del paciente y su ultima medicion registrada.
* **CareStore [Store]:** Estado compartido del contexto y unica puerta de entrada a los comandos `load` y `changeStatus`.
* **MeasurementAssessment [Servicio de dominio]:** Clasifica una medicion en normal, advertencia, peligro o desconocida usando los rangos de referencia del paciente.
* **Modelo de dominio [TypeScript]:** `Patient`, `CareAlert`, `CareRecord`, `Intervention`, `Caregiver`, `MeasurementRange`, `RecordType` y `CareSnapshot`, con el comportamiento asociado a cada uno.
* **CareService [HttpClient]:** Consulta y actualiza pacientes, alertas, registros, intervenciones, cuidadores y rangos de medicion, y traduce los objetos de transferencia a entidades del dominio.

#### 3. Componentes del contenedor Backend API planificado

\begin{center} \includegraphics[width=\linewidth]{assets/diagrams/c4-05-components-backend.png} \end{center}

Este diagrama mantiene el diseno objetivo del backend, que reemplazara a la API simulada. Ninguno de sus componentes esta desplegado:

* **IAM [Spring Security, JWT]:** Registro, autenticacion y autorizacion por roles.
* **Monitoring [Spring REST y servicios de aplicacion]:** Recepcion de telemetria biometrica y evaluacion de cada medicion contra la linea base del paciente.
* **Emergency Notification [Servicios de aplicacion y WebClient]:** Cola de alertas criticas y despacho asincrono hacia la red de apoyo familiar.
* **Triage & Scheduling [Servicios de aplicacion y cliente REST]:** Clasificacion de severidad clinica y pre-agendamiento asistido de consultas.
* **Profiles & Affiliations [Spring Data JPA]:** Pacientes, cuidadores y la vinculacion entre ambos, que hoy se resuelve con arreglos de identificadores en el cliente.
