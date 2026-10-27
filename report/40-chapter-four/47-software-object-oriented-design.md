## 4.7. Software Object-Oriented Design

### 4.7.1. Class Diagrams

El diagrama de clases (modelo táctico de DDD) detalla la implementación en código de los conceptos descubiertos durante el Design-Level Event Storming ([4.6.1](46-domain-driven-software-architecture.md)). Cada clase se rotula con el estereotipo táctico que le corresponde:

| Estereotipo | Definición | Ejemplos en VitaLink |
|:-----------------------------|:---------------------------------------------|:------------------------------------|
| «Aggregate Root (AR)» | Entidad raíz que define el límite de consistencia. Es la única que se carga desde el repositorio y la única que modifica los objetos internos | `VitalSignsTracker`, `EmergencyAlert`, `TriageAssessment`, `PatientProfile`, `UserAccount` |
| «Entity» | Objeto con identidad propia y ciclo de vida, interno a un aggregate | `BiometricRecord`, `AlertObservation`, `CaregiverAffiliation`, `MedicalAppointmentReservation` |
| «Value Object (VO)» | Objeto inmutable definido solo por sus atributos | `BiometricReading`, `Baseline`, `ObservedValue`, `NotificationChannel`, `ProviderAffiliation`, `TimeSlot` |
| «Enum» | Tipo cerrado para estados y clasificaciones | `PriorityLevel`, `AlertStatus`, `ReadingOrigin`, `UserRole`, `CaregiverRole` |
| «Domain Event (DE)» | Hecho ocurrido en el dominio, emitido por un AR y consumido por otros aggregates o contextos | `ThresholdExceeded`, `EmergencyAlertTriggered`, `AlertStatusChanged` |

: Estereotipos tácticos de DDD aplicados al modelo de VitaLink

El diagrama se elaboró como Diagram-as-Code con Mermaid; su código fuente se incluye en los anexos. Cada clase muestra atributos y métodos con visibilidad (`+` público, `-` privado, `#` protegido). Las transiciones de estado y las validaciones (invariantes) ocurren dentro de los métodos del Aggregate Root, de modo que los datos nunca queden en estados inválidos.

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.85\textheight,keepaspectratio]{assets/class-diagram.png}
\caption{Class Diagram del modelo táctico de VitaLink con estereotipos DDD}
\end{figure}

**Reglas transversales.** (1) Un aggregate solo referencia a otros por identificador (`patientId`, `alertId`, `userId`), nunca por objeto. (2) Cada transacción modifica un único aggregate. (3) La comunicación entre aggregates y entre Bounded Contexts se realiza mediante Domain Events, con consistencia eventual. (4) Los Aggregate Roots no ejecutan efectos de infraestructura (envío de mensajes, acceso a red): los emiten como eventos que procesan handlers o Domain Services.

#### 4.7.1.1. Monitoring Context

**Trazabilidad:** TS-01, TS-03, TS-09, US-14, US-18.

* **Aggregate Root:** `VitalSignsTracker`, identificado por `patientId`.
* **Entity:** `BiometricRecord` (`recordId`, `recordedAt`, `origin`).
* **Value Objects:** `BiometricReading` (tipo, valor, unidad) y `Baseline` (tipo, mínimo, máximo).
* **Enums:** `ReadingType` y `ReadingOrigin` (`DEVICE`, `ASSISTED`).
* **Domain Event emitido:** `ThresholdExceeded`.
* **Límite del aggregate:** incluye la `Baseline` vigente y la ventana reciente de registros necesaria para evaluar tendencias. El historial completo se consulta mediante un repositorio de lectura y no se carga en el aggregate.
* **Invariantes:** (1) todo `BiometricRecord` pertenece a un único `patientId`; (2) solo se acepta un registro si existe una `Baseline` para su tipo de lectura; (3) el `ReadingOrigin` es obligatorio, lo que diferencia las lecturas de dispositivo de las ingresadas en modo asistido; (4) un registro fuera del rango de la `Baseline` no se persiste sin emitir `ThresholdExceeded`.
* **Comportamiento:** `recordReading(reading, origin)` y `updateBaseline(baseline)`.

#### 4.7.1.2. Emergency & Notification Context

**Trazabilidad:** US-11 a US-13, US-15 a US-17, US-19, US-20, US-22, US-23, US-26, TS-02, TS-04, TS-05, TS-10.

* **Aggregate Root:** `EmergencyAlert`.
* **Entity:** `AlertObservation` (autor, texto, fecha; inmutable una vez creada).
* **Value Objects:** `ObservedValue` (valor, rango esperado, hora del suceso) y `NotificationChannel`.
* **Enums:** `PriorityLevel` y `AlertStatus` (`PENDING`, `IN_REVIEW`, `ATTENDED`).
* **Domain Events:** consume `ThresholdExceeded`, mediante un handler que crea la alerta, y emite `EmergencyAlertTriggered` y `AlertStatusChanged`.
* **Límite del aggregate:** la alerta, sus observaciones y su estado actual.
* **Invariantes:** (1) una alerta no puede crearse sin `PriorityLevel` ni `ObservedValue`; (2) los estados solo avanzan en el orden `PENDING` → `IN_REVIEW` → `ATTENDED`, y una alerta nunca se elimina ni se reabre; (3) solo puede haber un revisor activo mientras la alerta está `IN_REVIEW`; (4) las observaciones solo se agregan, nunca se modifican; (5) una alerta originada por SOS se crea con prioridad crítica.
* **Comportamiento:** `startReview(reviewerId)`, `markAttended(actorId)` y `addObservation(authorId, text)`.
* **Notificación:** el envío no lo realiza el aggregate. El Domain Service `NotificationDispatcher` se suscribe a `EmergencyAlertTriggered` y `AlertStatusChanged`, selecciona el `NotificationChannel` y la plantilla según el rol del destinatario (TS-10), e invoca el puerto de salida correspondiente.

#### 4.7.1.3. Triage & Scheduling Context

Este Bounded Context corresponde a la evolución del producto posterior al piloto. Las 37 historias del backlog actual no lo cubren, por lo que sus funcionalidades se incorporarán al backlog en sprints posteriores.

* **Aggregate Root:** `TriageAssessment`, asociado a una única alerta (`alertId`).
* **Entity:** `MedicalAppointmentReservation`.
* **Value Object:** `TimeSlot`.
* **Enum:** `TriageOutcome`.
* **Domain Event consumido:** `EmergencyAlertTriggered`.
* **Invariantes:** (1) un `TriageAssessment` se asocia a exactamente una alerta; (2) solo se crea una reserva cuando el `TriageOutcome` requiere atención programada.
* **Disponibilidad:** la verificación de disponibilidad horaria depende de otros aggregates, por lo que no es un invariante interno. La resuelve el Domain Service `SchedulingPolicy` y la reserva se confirma con consistencia eventual.

#### 4.7.1.4. IAM & Profile Context

**Trazabilidad:** US-24, TS-06, TS-07, TS-08, TS-11.

* **Aggregate Roots:** `UserAccount` (`userId`, `UserRole`) y `PatientProfile` (`patientId`).
* **Entity:** `CaregiverAffiliation` (interna a `PatientProfile`, con `CaregiverRole`).
* **Value Object:** `ProviderAffiliation` (identificador del proveedor, fecha de inicio).
* **Enums:** `UserRole` (`OLDER_ADULT`, `FAMILY_MEMBER`, `PHYSICIAN`) y `CaregiverRole` (`PRIMARY`, `SECONDARY`).
* **Domain Event emitido:** `CaregiverNetworkUpdated`.
* **Invariantes de `PatientProfile`:** (1) el monitoreo no se activa sin los datos mínimos del paciente (por ejemplo, DNI); (2) existe exactamente una `ProviderAffiliation` activa, lo que garantiza el aislamiento de datos por clínica; (3) la red de cuidado mantiene al menos un `CaregiverAffiliation` con rol `PRIMARY` activo.
* **Invariante de `UserAccount`:** cada usuario tiene un único rol, y todo acceso a datos clínicos se valida con el rol y la afiliación (JWT y RBAC).
* **Integración:** los demás contextos consultan este contexto por identificador (`patientId`, `userId`) para resolver destinatarios de notificaciones y aislar los datos clínicos.

#### 4.7.1.5. Matriz de trazabilidad historias → modelo táctico

| Historias | Bounded Context | Aggregate Root | Eventos / Comportamiento principal |
|:------------------|:--------------------------|:--------------------|:-------------------------------------------|
| US-01 a US-10, US-25 | Capa de presentación (Landing y UI) | No aplica | Sin lógica de dominio |
| TS-01, TS-09 | Monitoring | `VitalSignsTracker` | `recordReading()` → `ThresholdExceeded` |
| TS-03, US-14, US-18 | Monitoring | `VitalSignsTracker` | Consultas de lectura sobre `BiometricRecord` y estado de alertas |
| US-11, US-12, US-13, TS-02 | Emergency & Notification | `EmergencyAlert` | Consultas filtradas por `AlertStatus` y `PriorityLevel` |
| US-15, US-17, US-20, US-23, TS-04 | Emergency & Notification | `EmergencyAlert` | `startReview()`, `markAttended()` → `AlertStatusChanged` |
| US-16, TS-05 | Emergency & Notification | `EmergencyAlert` | `addObservation()` |
| US-19, US-22, US-26, TS-10 | Emergency & Notification | `EmergencyAlert` | `EmergencyAlertTriggered` → `NotificationDispatcher` |
| US-24, TS-06, TS-07, TS-08 | IAM & Profile | `PatientProfile` | `CaregiverNetworkUpdated` |
| TS-11 | IAM & Profile | `UserAccount` | Validación de JWT, rol y afiliación |

: Trazabilidad entre historias del backlog y el modelo táctico DDD