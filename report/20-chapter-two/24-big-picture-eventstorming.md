## 2.4. Big Picture Event Storming

El Big Picture identifica el recorrido de negocio de VitaLink: registrar identidad y red de cuidado, recibir lecturas, detectar desviaciones, coordinar alertas y confirmar su atención. El refinamiento táctico de [4.6.1](../40-chapter-four/46-domain-driven-software-architecture.md) conserva cuatro Bounded Contexts y diferencia el piloto de la evolución futura de triaje y citas.

| Bounded Context canónico | Recorrido | Eventos principales | Alcance |
|---|---|---|---|
| IAM & Profile | Registro, afiliación a proveedor y red de cuidado | UserRegistered, CaregiverNetworkUpdated | Diseño del piloto |
| Monitoring | Registro y evaluación de lecturas | VitalSignsRecorded, ThresholdExceeded | Diseño del piloto |
| Emergency & Notification | Crear alerta o SOS, revisar, atender y coordinar avisos | EmergencyAlertTriggered, AlertStatusChanged | Diseño del piloto |
| Triage & Scheduling | Evaluación y propuesta/confirmación de cita | RiskEvaluated, AppointmentPreScheduled, AppointmentConfirmed | Futuro, sin historias comprometidas en el backlog actual |

Las denominaciones preliminares Notification, Scheduling & Triage e IAM & Users se consolidan respectivamente como Emergency & Notification, Triage & Scheduling e IAM & Profile. «Confirmar recepción» es una acción, mientras AlertStatusChanged es el hecho que deja esa transición; la detección de caídas y el escalamiento automático por tiempo quedan como hipótesis pendientes de historias y validación. No se presentan como comportamiento ya implementado.

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.80\textheight,keepaspectratio]{assets/Big_Picture_Event_Storming.png}
\caption{Big Picture refinado: recorrido del piloto y evolución futura}
\end{figure}

**Actores:** familiares, adultos mayores y profesionales de salud. **Sistemas externos propuestos:** simulador de dispositivos, proveedor de notificaciones y agenda clínica. Los destinatarios y permisos se resuelven con la afiliación del paciente y la red de cuidado, mediante identificadores.

**Políticas y hotspots:** selección de avisos por rol, lecturas fuera de la línea base, competencia por revisar una alerta, cambios de contacto y fallos de entrega. La disponibilidad y confirmación de citas constituyen un hotspot futuro. Las reglas e invariantes se formalizan en 4.7; la publicación de eventos y los efectos externos pertenecen a aplicación e infraestructura.

El diagrama representa el diseño del dominio, no un flujo ejecutado por la fake API. Los fuentes Mermaid y las ampliaciones SVG están disponibles en [8.1](../80-annexes/81-annexes.md).
