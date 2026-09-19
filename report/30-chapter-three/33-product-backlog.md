## 3.3. Product Backlog.

El orden del Product Backlog responde al valor de negocio, no a la conveniencia técnica: las historias de Landing Page se consideran desde el primer sprint, y ninguna historia de seguridad, autenticación o control de acceso se ubica al inicio del backlog — se posicionan una vez que la funcionalidad que protegen ya tiene valor entregado.

### 3.3.1. Tabla de Backlog

| # Orden | User Story Id | Título | Descripción | Story Points (1/2/3/5/8) |
|---|---|---|---|---|
| 1 | US-01 | Entender la propuesta de valor en segundos | Como visitante médico, quiero entender en segundos qué problema resuelve VitaLink, para decidir si me interesa conocer más. | 1 |
| 2 | US-06 | Entender el beneficio sin llamadas constantes | Como familiar, quiero entender en segundos cómo la app me ayuda a saber del estado de mi padre/madre sin llamarlo constantemente, para decidir si me interesa registrarme. | 1 |
| 3 | US-07 | Confiar en quién ve los datos de salud | Como familiar, quiero ver una sección clara de privacidad que explique quién puede ver los datos de salud de mi familiar, para confiar en registrar su información. | 1 |
| 4 | US-02 | Confiar antes de registrar datos de pacientes | Como profesional de salud, quiero ver una sección de privacidad/seguridad de datos, para confiar en registrar información de mis pacientes. | 1 |
| 5 | US-09 | Entender la app sin tecnicismos | Como adulto mayor o su cuidador, quiero ver un mensaje simple (sin tecnicismos) que explique qué hace la app, para entender rápido si me sirve. | 1 |
| 6 | US-10 | Ver qué esperar antes de registrarse | Como visitante, quiero ver un ejemplo visual de cómo se ve una alerta o el dashboard, para saber qué esperar antes de registrarme. | 2 |
| 7 | US-05 | Ver un ejemplo visual de una alerta | Como profesional de salud, quiero ver un ejemplo visual simple de cómo se ve una alerta, para entender rápido cómo funciona el seguimiento. | 2 |
| 8 | US-08 | Conocer cómo funciona antes de crear cuenta | Como familiar, quiero un botón para "conocer cómo funciona" antes de crear una cuenta, para entender el proceso sin comprometerme aún. | 2 |
| 9 | US-04 | Unirme como proveedor de salud | Como profesional de salud, quiero un botón específico para "unirme como proveedor de salud", para iniciar mi registro directamente. | 2 |
| 10 | US-03 | Solicitar información antes de registrarse | Como profesional de salud, quiero un botón claro para "solicitar información" antes de registrarme, para evaluar la herramienta sin compromiso. | 2 |
| 11 | TS-01 | Ingesta de Telemetría Biométrica | Como sistema, quiero registrar un evento o Telemetría Biométrica capturada y generar automáticamente una alerta cuando el valor esté fuera de rango, para iniciar el flujo de atención sin depender de revisión manual. | 5 |
| 12 | TS-02 | Listado de alertas | Como sistema, quiero exponer un listado de alertas filtrable por estado y prioridad, para alimentar el dashboard médico y familiar. | 3 |
| 13 | US-18 | Estado general al abrir la app | Como familiar y adulto mayor, quiero ver un estado general simple ("todo bien" / "necesita atención") al abrir la app, para saber de inmediato si debo actuar. | 2 |
| 14 | US-19 | Recibir una alerta comprensible | Como familiar y adulto mayor, quiero recibir una alerta que indique qué pasó, qué tan grave es y si ya alguien está atendiendo la situación, para decidir si debo intervenir. | 3 |
| 15 | US-20 | Confirmar atención con un solo botón | Como familiar y adulto mayor, quiero confirmar con un solo botón que ya contacté o atendí a mi familiar, para que el resto de la familia sepa que el caso está cubierto. | 2 |
| 16 | US-11 | Resumen inicial de alertas pendientes | Como médico, quiero ver un resumen inicial con la cantidad de pacientes con alertas pendientes, para priorizar mi atención al iniciar el día. | 3 |
| 17 | US-12 | Nivel de urgencia visual | Como médico, quiero ver el nivel de urgencia de cada alerta de forma visual (color/etiqueta), para decidir rápido qué revisar primero. | 2 |
| 18 | US-15 | Marcar una alerta como revisada o atendida | Como médico, quiero marcar una alerta como "en revisión" o "atendida", para que otros sepan el estado del caso. | 3 |
| 19 | TS-04 | Transición de estado de una alerta | Como sistema, quiero cambiar el estado de una alerta (pendiente/en revisión/atendida/cerrada) sin eliminarla, registrando quién la atendió y cuándo, para conservar el historial completo. | 3 |
| 20 | TS-10 | Notificaciones diferenciadas por rol | Como sistema, quiero enviar notificaciones diferenciadas según el destinatario (familiar vs. médico), para que cada uno reciba solo la información relevante a su rol. | 5 |
| 21 | US-23 | Evitar duplicar esfuerzos entre familiares | Como familiar y adulto mayor, quiero saber si otro miembro de la familia ya revisó o atendió una alerta, para no duplicar esfuerzos ni generar confusión. | 2 |
| 22 | US-17 | Evitar revisiones duplicadas | Como médico, quiero ver si un caso ya fue revisado por otra persona, para evitar duplicar esfuerzos. | 2 |
| 23 | US-13 | Acceder al detalle de un paciente | Como médico, quiero acceder al detalle de un paciente desde el resumen, para revisar contexto sin buscar en varias pantallas. | 2 |
| 24 | US-14 | Historial ordenado por fecha | Como médico, quiero ver el historial de registros de un paciente ordenado por fecha, para entender su evolución sin papeles dispersos. | 3 |
| 25 | TS-03 | Historial Clínico Digital de paciente o adulto mayor | Como sistema, quiero almacenar y exponer el Historial Clínico Digital de un paciente, para permitir consultas posteriores desde el frontend médico y familiar. | 3 |
| 26 | US-16 | Agregar una observación breve | Como médico, quiero agregar una observación breve al atender una alerta, para dejar registro rápido de lo ocurrido. | 2 |
| 27 | TS-05 | Observaciones sobre una alerta | Como sistema, quiero registrar observaciones breves asociadas a una alerta, para dejar trazabilidad de lo ocurrido durante su atención. | 2 |
| 28 | US-21 | Historial simple sin preguntar directamente | Como familiar y adulto mayor, quiero ver un historial simple de días anteriores, para revisar el bienestar de mi familiar sin tener que preguntarle directamente. | 3 |
| 29 | US-22 | Ver el dato que originó una alerta | Como familiar y adulto mayor, quiero ver el dato específico que originó una alerta (ej. presión alta), para entender la gravedad real. | 2 |
| 30 | US-24 | Mantener actualizada la red familiar | Como familiar y adulto mayor, quiero actualizar mis datos de contacto y ver quiénes más forman parte de la red familiar autorizada, para mantener la información al día. | 3 |
| 31 | US-26 | Pedir ayuda rápido en una urgencia | Como familiar y adulto mayor, quiero poder avisar rápido que necesito ayuda sin tener que explicar mucho, para pedir asistencia en momentos de urgencia. | 2 |
| 32 | US-25 | Modo de uso extremadamente simple | Como familiar y adulto mayor, quiero un modo de uso extremadamente simple (botones grandes, pocos pasos), para poder usarlo sin depender siempre de ayuda. | 5 |
| 33 | TS-09 | Registro en modo asistido | Como sistema, quiero registrar un modo "asistido" donde un cuidador ingresa datos en nombre del adulto mayor, para cubrir los casos donde el usuario final no puede operar la tecnología directamente. | 2 |
| 34 | TS-08 | Red familiar con roles | Como sistema, quiero permitir múltiples familiares autorizados por adulto mayor con roles diferenciados (principal/secundario), para reflejar cómo se distribuyen las responsabilidades de cuidado. | 3 |
| 35 | TS-06 | Asociación paciente–proveedor de salud | Como sistema, quiero asociar a cada paciente un proveedor de salud (si existe), para vincular la información clínica correspondiente. | 2 |
| 36 | TS-07 | Validación de datos mínimos | Como sistema, quiero validar que los datos básicos de un paciente estén completos antes de activar su seguimiento, para asegurar información mínima confiable. | 2 |
| 37 | TS-11 | Control de acceso a datos de salud (RBAC) | Como sistema, quiero registrar el nivel de acceso de cada usuario a los datos de salud del adulto mayor, para cumplir con las expectativas de privacidad expresadas por los entrevistados. | 5 |

**Total:** 37 historias · 91 Story Points.

### 3.3.2. Tablero público del Backlog

**Herramienta:** `[completar — Trello / Jira / YouTrack / Pivotal Tracker]`
**URL pública:** `[completar]`

<!-- \includegraphics[width=0.9\linewidth]{assets/product-backlog.png} -->
