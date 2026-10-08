## 4.7. Software Object-Oriented Design

### 4.7.1. Class Diagrams

El modelo táctico especifica el diseño de dominio refinado desde [4.6.1](46-domain-driven-software-architecture.md). Sus cinco Aggregate Roots pertenecen a los mismos cuatro Bounded Contexts. Los diagramas muestran el diseño propuesto para el backend; no se atribuye esta implementación a la fake API de TB1.

| Estereotipo | Significado | Elementos principales |
|---|---|---|
| AR, Aggregate Root | Raíz y límite de consistencia; controla cambios de sus objetos internos | VitalSignsTracker, EmergencyAlert, UserAccount, PatientProfile, TriageAssessment |
| Entity | Identidad y ciclo de vida dentro de un aggregate | BiometricRecord, AlertObservation, CaregiverAffiliation, MedicalAppointmentReservation |
| VO, Value Object | Valor inmutable, sin identidad ni efectos de infraestructura | BiometricReading, Baseline, ObservedValue, NotificationChannel, ProviderAffiliation, TimeSlot |
| Enum | Estados o clasificaciones cerradas | ReadingType, ReadingOrigin, AlertOrigin, AlertStatus, PriorityLevel, UserRole, CaregiverRole, TriageOutcome |
| DE, Domain Event | Hecho inmutable emitido por la transición de una raíz | VitalSignsRecorded, ThresholdExceeded, EmergencyAlertTriggered, AlertStatusChanged, UserRegistered, CaregiverNetworkUpdated; eventos futuros de Triage |
| DomainService | Política de negocio sin I/O ni estado persistente propio | RoleBasedNotificationPolicy, SchedulingPolicy |

En UML, el prefijo `-` identifica atributos privados y `+` operaciones públicas. La composición y su multiplicidad delimitan los objetos internos; las dependencias entre raíces usan IDs. Los namespaces con sufijo Aggregate delimitan cada agregado. Las notas de invariantes se corresponden con las tablas siguientes. Se separan las composiciones de aggregate de sus enums y eventos para conservar legibilidad; las raíces sin miembros en figuras complementarias son referencias a las definiciones completas, no aggregates adicionales. Los diagramas muestran los nombres de las operaciones; sus parámetros se omiten en la vista resumida y se precisan al implementar el backend. Los VOs se validan al construirse y no exponen setters; las entidades internas solo cambian por operaciones de la raíz.

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.80\textheight,keepaspectratio]{assets/class-diagram.png}
\caption{Vista general de Aggregate Roots y referencias por identificador}
\end{figure}

#### 4.7.1.1. Monitoring Context

**Trazabilidad:** TS-01, TS-03, TS-09, US-14, US-18 y US-21.

VitalSignsTracker, identificado por patientId, conserva la línea base vigente y la ventana reciente de BiometricRecord necesaria para evaluar lecturas. BiometricReading representa tipo, valor y unidad; ReadingOrigin diferencia DEVICE de ASSISTED. El historial completo se consulta en un modelo de lectura independiente, sin convertirlo en otro aggregate.

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.80\textheight,keepaspectratio]{assets/class-monitoring.png}
\caption{Monitoring: límite de aggregate, raíz, entidad y Value Objects}
\end{figure}

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.88\textheight,keepaspectratio]{assets/class-monitoring-types-events.png}
\caption{Monitoring: enums y eventos; la raíz se muestra como referencia}
\end{figure}


| Regla | Invariante / responsabilidad | Operación |
|---|---|---|
| M-01 | Cada registro de la ventana pertenece al patientId de la raíz | recordReading() |
| M-02 | Existe una Baseline válida del mismo tipo y unidad; mínimo no supera máximo | recordReading(), updateBaseline() |
| M-03 | La lectura tiene origen y fecha del suceso obligatorios | recordReading() |
| M-04 | Una lectura aceptada emite VitalSignsRecorded; si excede la Baseline, produce además ThresholdExceeded en la misma transición | recordReading() |

Una desviación no invalida la lectura: debe conservarse para el historial y originar el evento correspondiente. Baseline y BiometricReading son valores inmutables. El evento transporta el valor, el rango y la hora del suceso necesarios para crear la alerta.

#### 4.7.1.2. Emergency & Notification Context

**Trazabilidad:** US-11 a US-13, US-15 a US-17, US-19, US-20, US-22, US-23, US-26, TS-02, TS-04, TS-05 y TS-10.

EmergencyAlert es la raíz; AlertObservation es una entidad interna que conserva autor, texto y fecha. ObservedValue conserva tipo de lectura, unidad, valor, rango y fecha del snapshot biométrico para una alerta originada en TELEMETRY. Una alerta SOS tiene origen explícito y prioridad CRITICAL, sin inventar un valor biométrico: por eso la multiplicidad de ObservedValue es 0..1.

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.80\textheight,keepaspectratio]{assets/class-emergency-notification.png}
\caption{EmergencyAlert: raíz, observaciones y valor observado}
\end{figure}

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.88\textheight,keepaspectratio]{assets/class-emergency-types-events.png}
\caption{EmergencyAlert: tipos y eventos; la raíz se muestra como referencia}
\end{figure}

\begin{figure}[htbp]
\centering
\includegraphics[width=0.85\linewidth,height=0.88\textheight,keepaspectratio]{assets/class-notification-policy.png}
\caption{Política pura de notificación y Value Object del canal}
\end{figure}


| Regla | Invariante / responsabilidad | Operación |
|---|---|---|
| E-01 | Origen y prioridad obligatorios; TELEMETRY requiere ObservedValue y SOS requiere prioridad CRITICAL | Creación de EmergencyAlert |
| E-02 | PENDING pasa a IN_REVIEW o ATTENDED; IN_REVIEW pasa a ATTENDED; ATTENDED es terminal y la alerta no se elimina | startReview(), markAttended() |
| E-03 | Solo un revisor activo puede ocupar una alerta en IN_REVIEW; una operación concurrente no sobrescribe esa asignación | startReview() |
| E-04 | Las observaciones se agregan con identidad, autor y fecha; no se editan ni se eliminan | addObservation() |
| E-05 | Crear la alerta emite EmergencyAlertTriggered; cambiar su estado emite AlertStatusChanged con el actor responsable | Operaciones de la raíz |

La transición directa PENDING → ATTENDED permite la confirmación de una sola acción de US-20; no obliga a que el familiar abra una revisión clínica como paso de interfaz adicional. El texto «Acompañada» de US-20 corresponde a la presentación de esa confirmación. El valor REVIEW del ejemplo de transporte de TS-04 se traduce a IN_REVIEW en el dominio; esta sección no modifica endpoints ni código del frontend.

El handler de ThresholdExceeded crea la alerta a partir de un contrato de integración. El handler de notificaciones recibe los eventos de EmergencyAlert, consulta destinatarios por IDs y usa RoleBasedNotificationPolicy. La política selecciona NotificationChannel sin enviar mensajes; la aplicación invoca el puerto de salida. NotificationChannel no tiene identidad ni operación dispatch().

#### 4.7.1.3. Triage & Scheduling Context, evolución futura

Este contexto no está comprometido en las 37 historias del backlog actual. Su diseño reserva un límite para futuras historias de evaluación y citas; no acredita funcionalidades realizadas en Sprint 1 o Sprint 2.

TriageAssessment es una raíz asociada a alertId. MedicalAppointmentReservation pertenece a esa raíz; TimeSlot es un VO con proveedor e intervalo válido. Los eventos previstos son RiskEvaluated, AppointmentPreScheduled y AppointmentConfirmed.

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.80\textheight,keepaspectratio]{assets/class-triage-scheduling.png}
\caption{UML de Triage \& Scheduling: diseño futuro y reserva interna}
\end{figure}

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.88\textheight,keepaspectratio]{assets/class-triage-types-events.png}
\caption{Triage futuro: tipos, eventos y política; la raíz se muestra como referencia}
\end{figure}


| Regla | Invariante / responsabilidad | Operación |
|---|---|---|
| T-01 | Cada assessment se vincula a exactamente una alerta por alertId | Creación de TriageAssessment |
| T-02 | Solo se propone una reserva cuando TriageOutcome requiere atención programada; existe como máximo una reserva activa en esta versión del diseño | proposeAppointment() |
| T-03 | La propuesta no implica confirmación externa; la confirmación se registra con la referencia de la reserva | confirmAppointment() |

SchedulingPolicy selecciona un TimeSlot a partir de disponibilidad suministrada por la aplicación. La consulta y confirmación con la agenda dependen de un adaptador externo y de consistencia eventual, no de una supuesta transacción interna con otro sistema.

#### 4.7.1.4. IAM & Profile Context

**Trazabilidad:** US-24, TS-06, TS-07, TS-08 y TS-11.

UserAccount y PatientProfile son raíces independientes. UserAccount conserva el rol y estado del usuario. PatientProfile controla CaregiverAffiliation y ProviderAffiliation; las afiliaciones familiares referencian userId sin contener un UserAccount. UserRegistered y CaregiverNetworkUpdated describen sus hechos de dominio.

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.80\textheight,keepaspectratio]{assets/class-iam-profile.png}
\caption{PatientProfile: raíz y afiliaciones internas del aggregate}
\end{figure}

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.88\textheight,keepaspectratio]{assets/class-iam-account-types-events.png}
\caption{IAM: UserAccount, enums y eventos; PatientProfile se muestra como referencia}
\end{figure}


| Regla | Invariante / responsabilidad | Operación |
|---|---|---|
| I-01 | No se activa monitoreo sin los datos mínimos válidos del paciente | activateMonitoring() |
| I-02 | Con monitoreo activo existe exactamente una ProviderAffiliation vigente | activateMonitoring(), assignProvider() |
| I-03 | Con monitoreo activo existe al menos un cuidador PRIMARY activo; modificar la red no rompe esa condición | linkCaregiver(), updateCaregiverContact() |
| I-04 | El rol de UserAccount es uno de UserRole y su cambio conserva un único rol | Creación, changeRole() |
| I-05 | Cambiar contactos o afiliaciones de la red emite CaregiverNetworkUpdated | Operaciones de PatientProfile |

La multiplicidad 0..1 de ProviderAffiliation y 0..* de CaregiverAffiliation permite preparar un perfil antes de activar el monitoreo; I-02 e I-03 restringen el estado activo. La aplicación valida identidad, rol y pertenencia al proveedor antes de cada acceso. JWT y RBAC son mecanismos del servidor y sus adaptadores; no se declara que la fake API los implemente.

#### 4.7.1.5. Matriz de trazabilidad historias → modelo táctico

| Historias | Bounded Context / capa | Raíz / modelo de lectura | Comportamiento |
|---|---|---|---|
| US-01 a US-10, US-25 | Presentación | No aplica | Landing y simplicidad de UI |
| TS-01, TS-09 | Monitoring | VitalSignsTracker | recordReading(); VitalSignsRecorded y ThresholdExceeded |
| TS-03, US-14, US-21 | Monitoring | Historial de BiometricRecord | Consulta cronológica |
| US-18 | Monitoring + Emergency & Notification | Modelos de lectura por patientId | Estado general y alertas |
| US-11, US-12, TS-02 | Emergency & Notification | Modelo de lectura de EmergencyAlert | Listar por estado y prioridad |
| US-13 | Emergency & Notification + Monitoring + IAM & Profile | Consulta por alertId/patientId | Detalle del paciente autorizado |
| US-15, US-17, US-20, US-23, TS-04 | Emergency & Notification | EmergencyAlert | startReview(), markAttended(); AlertStatusChanged |
| US-16, TS-05 | Emergency & Notification | EmergencyAlert | addObservation() |
| US-19, US-22, US-26, TS-10 | Emergency & Notification | EmergencyAlert | Evento de creación, dato observado o SOS y avisos por rol |
| US-24, TS-06, TS-07, TS-08 | IAM & Profile | PatientProfile | Afiliaciones, contactos y CaregiverNetworkUpdated |
| TS-11 | IAM & Profile + aplicación | UserAccount y afiliación por identificador | Autorizar en servidor |
| Futuras historias, aún no comprometidas | Triage & Scheduling | TriageAssessment | Evaluación y coordinación de reserva |

La coordinación de consultas no comparte entidades entre contextos ni convierte las vistas del frontend en nuevos Bounded Contexts. Los fuentes editables, PNG y SVG de las figuras se incluyen en [8.1](../80-annexes/81-annexes.md).
