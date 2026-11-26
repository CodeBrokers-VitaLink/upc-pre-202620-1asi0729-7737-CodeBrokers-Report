## 4.6. Domain-Driven Software Architecture

VitaLink utiliza un monolito modular Java organizado alrededor de IAM, Providers, Enrollment y Care, con infraestructura transversal en Shared. La aplicación Angular y la Landing Page consumen y presentan distintos recorridos. Los siguientes diagramas aplican el modelo C4 (Brown, s. f.) a las revisiones de código del Anexo A. El corte exacto de producción requiere confirmación del equipo.

### 4.6.1. Design-Level Event Storming

El Design-Level Event Storming de AV2 desarrolló el Big Picture de 2.4 y propuso cuatro contextos, comandos, eventos, agregados y modelos de lectura. Se conserva como antecedente de diseño. Los nombres y escenarios de este artefacto describen la propuesta de aquella etapa.

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

VitaLink proporciona una experiencia web para el familiar o cuidador, el profesional de salud y el adulto mayor con acceso de autocuidado. El médico consulta casos vinculados y puede registrar intervenciones y observaciones. El familiar y el paciente consultan la información disponible según su vínculo. Resend es el proveedor implementado para el correo de observaciones cuando se configura. El registro de colegiaturas usa un catálogo ficticio incluido en el backend.

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.79\textheight,keepaspectratio]{assets/diagrams/c4-01-context.png}
\caption{Contexto del sistema VitaLink}
\end{figure}

### 4.6.3. Software Architecture Container Diagrams

La Landing Page es un sitio estático de GitHub Pages. La SPA Angular 22.2 se configura como sitio estático en Render y enlaza a la API de Spring Boot 4.0.6 y Java 26 desplegable como servicio Docker en Render. La aplicación accede a la API por HTTPS y JSON. Las rutas privadas requieren una sesión bearer. JDBC y Spring Data JPA gestionan la persistencia. Compose utiliza MySQL y la guía de producción describe TiDB Cloud por JDBC con TLS. El acceso a la API pública se documenta en 5.2.4.6. La base y el servicio de correo se representan según lo configurado en código o en las guías de despliegue.

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.79\textheight,keepaspectratio]{assets/diagrams/c4-02-container.png}
\caption{Contenedores de aplicación y almacenamiento de VitaLink}
\end{figure}

### 4.6.4. Software Architecture Component Diagrams

#### Landing Page

`index.html` organiza el contenido y sus metadatos, `styles.css` aporta el sistema visual y `script.js` controla el selector de audiencia, las traducciones y el menú. Los CTA abren el acceso de la SPA.

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.79\textheight,keepaspectratio]{assets/diagrams/c4-06-components-landing.png}
\caption{Componentes de la Landing Page}
\end{figure}

#### Web Application

La SPA utiliza rutas protegidas por rol (Angular, s. f.-b), stores de aplicación y servicios HTTP. El contexto IAM mantiene la sesión y los interceptores agregan la cabecera de autorización. Enrollment orquesta el alta por medio de un puerto. Care reúne los paneles, fichas, alertas, observaciones y notificaciones. Los assemblers traducen los recursos JSON a los modelos de interfaz. La localización de la SPA carga diccionarios ES/EN.

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.79\textheight,keepaspectratio]{assets/diagrams/c4-03-components-iam.png}
\caption{Componentes SPA de IAM y Enrollment}
\end{figure}

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.79\textheight,keepaspectratio]{assets/diagrams/c4-04-components-care.png}
\caption{Componentes SPA de Care}
\end{figure}

#### Backend REST API

Los controllers delegan en servicios de aplicación. Las escrituras y lecturas tienen responsables diferenciados mediante interfaces de comandos y consultas. Comparten la misma persistencia y forman parte del mismo proceso. Los recursos y assemblers separan el contrato HTTP de las clases de dominio.

IAM verifica el hash y vigencia de la sesión bearer y utiliza BCrypt para credenciales. Care verifica acceso por rol y vínculo. Enrollment orquesta el alta mediante puertos de cuenta, catálogo y paciente. Providers ofrece el directorio persistido y un catálogo de colegiaturas ficticio. El worker de Care toma notificaciones pendientes y usa el adaptador Resend (s. f.) si se habilita el correo. La separación de paquetes y casos de uso muestra la aplicación de DDD y una separación lógica de comandos y consultas. Los eventos del Event Storming pertenecen al diseño.

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.79\textheight,keepaspectratio]{assets/diagrams/c4-05-components-backend.png}
\caption{Componentes de la API para IAM, Providers y Enrollment}
\end{figure}

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.79\textheight,keepaspectratio]{assets/diagrams/c4-07-components-backend-care.png}
\caption{Componentes de la API para Care}
\end{figure}

El contenedor de almacenamiento conserva una estructura relacional compartida. La descomposición de sus tablas y sus vínculos se presenta en 4.8.1.
