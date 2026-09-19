# 3. Capítulo III: Requirements Specification

## 3.1. User Stories

Las User Stories de VitaLink se derivan de las 6 entrevistas registradas ([2.2. Entrevistas](../20-chapter-two/22-entrevistas.md)) para los segmentos Profesionales de Salud y Familiares/Adultos Mayores. Las historias de Landing Page usan como rol base *visitante* (con el subconjunto de segmento cuando aplica), y las Technical Stories del API RESTful usan el rol *Developer*, describiendo el escenario de interacción request/response en Gherkin.

\begin{longtable}{|p{0.10\textwidth}|p{0.17\textwidth}|p{0.22\textwidth}|p{0.40\textwidth}|p{0.09\textwidth}|}

\hline

\textbf{Epic / Story ID} &
\textbf{Título} &
\textbf{Descripción} &
\textbf{Criterios de Aceptación} &
\textbf{Relacionado con (Epic ID)} \\

\hline

EP-01 &
Captación y Confianza (Landing Page) &
Comunicar la propuesta de valor de VitaLink a ambos segmentos y convertir visitantes en usuarios registrados. &
--- &
--- \\

\hline

US-01 &
Entender la propuesta de valor en segundos &
Como visitante del segmento profesionales de salud, quiero entender en segundos qué problema resuelve VitaLink, para decidir si me interesa conocer más. &
\textbf{Given:} un visitante del segmento profesionales de salud ingresa por primera vez al sitio.\newline
\textbf{When:} revisa el contenido inicial.\newline
\textbf{Then:} identifica el problema que resuelve VitaLink sin necesidad de desplazamiento adicional. &
EP-01 \\

\hline

US-02 &
Confiar antes de registrar datos de pacientes &
Como visitante del segmento profesionales de salud, quiero conocer las medidas de privacidad y seguridad de datos, para confiar en registrar información de mis pacientes. &
\textbf{Given:} un visitante del segmento profesionales de salud.\newline
\textbf{When:} revisa el contenido de seguridad de la plataforma.\newline
\textbf{Then:} encuentra referencias explícitas a cifrado, cumplimiento normativo y control de acceso a los datos. &
EP-01 \\

\hline

US-03 &
Solicitar información antes de registrarse &
Como visitante del segmento profesionales de salud, quiero solicitar información antes de registrarme, para evaluar la herramienta sin compromiso. &
\textbf{Given:} un visitante del segmento profesionales de salud interesado pero no convencido.\newline
\textbf{When:} solicita información de contacto.\newline
\textbf{Then:} el sistema registra la solicitud sin exigir la creación de una cuenta. &
EP-01 \\

\hline

US-04 &
Unirme como proveedor de salud &
Como visitante del segmento profesionales de salud, quiero iniciar mi registro como proveedor, para afiliarme a la red de VitaLink. &
\textbf{Given:} un visitante del segmento profesionales de salud decidido a afiliarse.\newline
\textbf{When:} inicia el registro como proveedor.\newline
\textbf{Then:} el sistema lo dirige a un flujo de registro diferenciado del registro de familiares. &
EP-01 \\

\hline

US-05 &
Ver un ejemplo de cómo funciona una alerta &
Como visitante del segmento profesionales de salud, quiero conocer un ejemplo de cómo se comunica una alerta, para entender el funcionamiento del seguimiento antes de registrarme. &
\textbf{Given:} un visitante del segmento profesionales de salud.\newline
\textbf{When:} revisa el contenido sobre el funcionamiento de las alertas.\newline
\textbf{Then:} identifica el nivel de urgencia, el paciente asociado y la acción disponible sin documentación adicional. &
EP-01 \\

\hline

US-06 &
Entender el beneficio sin llamadas constantes &
Como visitante del segmento familiares, quiero entender en segundos cómo la plataforma me informa del estado de mi familiar sin llamarlo constantemente, para decidir si me interesa registrarme. &
\textbf{Given:} un visitante del segmento familiares ingresa por primera vez al sitio.\newline
\textbf{When:} revisa el contenido inicial.\newline
\textbf{Then:} identifica el beneficio de monitoreo remoto sin depender de llamadas frecuentes. &
EP-01 \\

\hline

US-07 &
Confiar en quién ve los datos de salud &
Como visitante del segmento familiares, quiero conocer quién puede ver los datos de salud de mi familiar, para confiar en registrar su información. &
\textbf{Given:} un visitante del segmento familiares evaluando registrar a su adulto mayor.\newline
\textbf{When:} revisa el contenido de privacidad.\newline
\textbf{Then:} encuentra una explicación de qué roles acceden a qué datos. &
EP-01 \\

\hline

US-08 &
Conocer cómo funciona antes de crear cuenta &
Como visitante del segmento familiares, quiero conocer cómo funciona la plataforma antes de crear una cuenta, para entender el proceso sin comprometerme aún. &
\textbf{Given:} un visitante del segmento familiares indeciso sobre registrarse.\newline
\textbf{When:} revisa el contenido explicativo del funcionamiento.\newline
\textbf{Then:} accede a la explicación del flujo Sentir $\rightarrow$ Analizar $\rightarrow$ Actuar sin que se le solicite ningún dato personal. &
EP-01 \\

\hline

US-09 &
Entender la plataforma sin tecnicismos &
Como visitante del segmento adultos mayores, quiero entender en lenguaje simple qué hace la plataforma, para saber rápido si me sirve. &
\textbf{Given:} un visitante del segmento adultos mayores con baja familiaridad tecnológica.\newline
\textbf{When:} revisa el mensaje principal del sitio.\newline
\textbf{Then:} el contenido evita jerga médica o técnica y comunica el beneficio en una sola idea. &
EP-01 \\

\hline

US-10 &
Ver qué esperar antes de registrarse &
Como visitante, quiero ver una representación de una alerta o del panel de control, para saber qué esperar antes de registrarme. &
\textbf{Given:} un visitante del segmento familiares.\newline
\textbf{When:} revisa el contenido que ilustra el panel de control.\newline
\textbf{Then:} visualiza una representación del panel familiar antes de crear una cuenta. &
EP-01 \\

\hline

EP-02 &
Monitoreo Clínico y Gestión de Alertas &
Dar a los profesionales de salud una vista operativa de sus pacientes y del ciclo de vida de cada alerta. &
--- &
--- \\

\hline

US-11 &
Resumen inicial de alertas pendientes &
Como médico, quiero un resumen con la cantidad de pacientes con alertas pendientes, para priorizar mi atención al iniciar el día. &
\textbf{Given:} un médico con sesión iniciada.\newline
\textbf{When:} accede al panel principal.\newline
\textbf{Then:} el sistema presenta la cantidad de alertas pendientes agrupadas por nivel de urgencia. &
EP-02 \\

\hline

US-12 &
Nivel de urgencia diferenciado &
Como médico, quiero identificar el nivel de urgencia de cada alerta, para decidir rápido cuál revisar primero. &
\textbf{Given:} una lista de alertas del médico.\newline
\textbf{When:} revisa cada alerta.\newline
\textbf{Then:} cada una indica su nivel de urgencia sin requerir abrir el detalle. &
EP-02 \\

\hline

US-13 &
Acceder al detalle de un paciente &
Como médico, quiero acceder al detalle de un paciente desde una alerta, para revisar su contexto sin buscarlo por separado. &
\textbf{Given:} una alerta asociada a un paciente.\newline
\textbf{When:} el médico selecciona esa alerta.\newline
\textbf{Then:} el sistema presenta el detalle del paciente asociado. &
EP-02 \\

\hline

US-14 &
Historial ordenado por fecha &
Como médico, quiero consultar el historial de un paciente ordenado por fecha, para entender su evolución. &
\textbf{Given:} el detalle de un paciente con registros previos.\newline
\textbf{When:} el médico consulta su historial.\newline
\textbf{Then:} los registros se presentan en orden cronológico descendente. &
EP-02 \\

\hline

US-15 &
Marcar una alerta como revisada o atendida &
Como médico, quiero cambiar el estado de una alerta a ``en revisión'' o ``atendida'', para que el equipo conozca el estado del caso. &
\textbf{Given:} una alerta en estado pendiente.\newline
\textbf{When:} el médico marca la alerta como ``en revisión'' o ``atendida''.\newline
\textbf{Then:} el sistema actualiza el estado de forma visible para los usuarios con acceso, conservando el registro original. &
EP-02 \\

\hline

US-16 &
Agregar una observación a una alerta &
Como médico, quiero registrar una observación breve al atender una alerta, para dejar constancia de lo ocurrido. &
\textbf{Given:} una alerta que el médico acaba de atender.\newline
\textbf{When:} registra una observación.\newline
\textbf{Then:} la observación queda asociada a la alerta y disponible en el historial del paciente. &
EP-02 \\

\hline

US-17 &
Evitar revisiones duplicadas &
Como médico, quiero saber si un caso ya fue revisado por otra persona, para evitar duplicar esfuerzos. &
\textbf{Given:} una alerta ya marcada ``en revisión'' por otro profesional.\newline
\textbf{When:} el médico accede a esa alerta.\newline
\textbf{Then:} el sistema indica quién la está revisando y desde cuándo. &
EP-02 \\

\hline

EP-03 &
Acompañamiento Familiar y Autocuidado &
Permitir que familiares y adultos mayores sigan el estado de salud y actúen ante una alerta. &
--- &
--- \\

\hline

US-18 &
Estado general al abrir la app &
Como familiar y adulto mayor, quiero ver un estado general simple al abrir la aplicación, para saber de inmediato si debo actuar. &
\textbf{Given:} un usuario familiar o adulto mayor con sesión iniciada.\newline
\textbf{When:} abre la aplicación.\newline
\textbf{Then:} el sistema presenta un indicador de estado general sin requerir interpretar datos crudos. &
EP-03 \\

\hline

US-19 &
Recibir una alerta comprensible &
Como familiar y adulto mayor, quiero recibir una alerta que indique qué ocurrió, su gravedad y si ya está siendo atendida, para decidir si debo intervenir. &
\textbf{Given:} un evento fuera de la línea base de un adulto mayor.\newline
\textbf{When:} el sistema genera la alerta correspondiente.\newline
\textbf{Then:} el destinatario recibe la causa, el nivel de gravedad y el estado de atención actual. &
EP-03 \\

\hline

US-20 &
Confirmar atención con una acción simple &
Como familiar y adulto mayor, quiero confirmar que ya atendí una situación, para que el resto de la familia sepa que el caso está cubierto. &
\textbf{Given:} una alerta activa.\newline
\textbf{When:} el usuario confirma la atención.\newline
\textbf{Then:} el sistema marca la alerta como atendida por esa persona, visible para el resto de la red familiar autorizada. &
EP-03 \\

\hline

US-21 &
Historial simple sin preguntar directamente &
Como familiar y adulto mayor, quiero consultar un historial simplificado de días anteriores, para revisar el bienestar de mi familiar sin preguntarle directamente. &
\textbf{Given:} un usuario en la vista de historial.\newline
\textbf{When:} selecciona un rango de días anteriores.\newline
\textbf{Then:} el sistema presenta un resumen simplificado del estado diario. &
EP-03 \\

\hline

US-22 &
Ver el dato que originó una alerta &
Como familiar y adulto mayor, quiero conocer el dato específico que originó una alerta, para entender la gravedad real. &
\textbf{Given:} una alerta abierta por el usuario.\newline
\textbf{When:} consulta su detalle.\newline
\textbf{Then:} el sistema muestra el valor medido, el rango esperado y la desviación detectada. &
EP-03 \\

\hline

US-23 &
Evitar duplicar esfuerzos entre familiares &
Como familiar y adulto mayor, quiero saber si otro familiar ya revisó o atendió una alerta, para no duplicar esfuerzos. &
\textbf{Given:} una alerta ya atendida por otro familiar autorizado.\newline
\textbf{When:} otro familiar la consulta.\newline
\textbf{Then:} el sistema indica quién la atendió y en qué momento. &
EP-03 \\

\hline

US-24 &
Mantener actualizada la red familiar &
Como familiar y adulto mayor, quiero actualizar mis datos de contacto y consultar la red familiar autorizada, para mantener la información al día. &
\textbf{Given:} un usuario en la configuración de su perfil.\newline
\textbf{When:} actualiza su información de contacto o consulta la red familiar.\newline
\textbf{Then:} el sistema guarda los cambios y los refleja para el resto de la red autorizada. &
EP-03 \\

\hline

US-25 &
Modo de uso extremadamente simple &
Como familiar y adulto mayor, quiero operar la aplicación con el mínimo de pasos posible, para usarla sin depender siempre de ayuda. &
\textbf{Given:} un adulto mayor operando la aplicación por sí mismo.\newline
\textbf{When:} accede a una función principal.\newline
\textbf{Then:} la completa en un máximo de dos pasos. &
EP-03 \\

\hline

US-26 &
Pedir ayuda rápido en una urgencia &
Como familiar y adulto mayor, quiero solicitar ayuda de forma inmediata sin explicaciones extensas, para pedir asistencia en una urgencia. &
\textbf{Given:} un adulto mayor en una situación de urgencia.\newline
\textbf{When:} solicita ayuda inmediata.\newline
\textbf{Then:} el sistema notifica de inmediato a la red familiar autorizada sin exigir información adicional. &
EP-03 \\

\hline

EP-04 &
Plataforma de Datos y Alertas (API) &
Sostener con datos confiables y trazables el flujo Sentir $\rightarrow$ Analizar $\rightarrow$ Actuar entre wearables, backend e IA. &
--- &
--- \\

\hline

TS-01 &
Ingesta de Telemetría Biométrica &
Como Developer, quiero un endpoint que reciba Telemetría Biométrica y genere una alerta automáticamente cuando el valor se desvíe de su Línea Base de Signos Vitales, para iniciar el flujo de atención sin revisión manual. &
\textbf{Given:} un payload válido con Telemetría Biométrica.\newline
\textbf{When:} se envía \texttt{POST /api/v1/events}.\newline
\textbf{Then:} el sistema responde 201 y persiste el evento.\newline
\textbf{Given:} un valor fuera de la Línea Base de Signos Vitales.\newline
\textbf{When:} el evento se procesa.\newline
\textbf{Then:} el sistema crea automáticamente una alerta con prioridad asignada. &
EP-04 \\

\hline

TS-02 &
Listado de alertas &
Como Developer, quiero un endpoint que liste alertas filtrables por estado y prioridad, para alimentar el panel médico y familiar. &
\textbf{Given:} alertas existentes con distintos estados y prioridades.\newline
\textbf{When:} se envía \texttt{GET /api/v1/alerts} con filtros.\newline
\textbf{Then:} el sistema responde 200 con únicamente las alertas que cumplen los filtros, ordenadas por prioridad. &
EP-04 \\

\hline

TS-03 &
Historial Clínico Digital &
Como Developer, quiero un endpoint que exponga el Historial Clínico Digital de un paciente, para permitir su consulta desde el frontend médico y familiar. &
\textbf{Given:} un paciente con eventos y alertas registrados.\newline
\textbf{When:} se envía \texttt{GET /api/v1/patients/\{id\}/history}.\newline
\textbf{Then:} el sistema responde 200 con el historial ordenado cronológicamente. &
EP-04 \\

\hline

TS-04 &
Transición de estado de una alerta &
Como Developer, quiero un endpoint que cambie el estado de una alerta sin eliminarla y registre quién hizo el cambio, para mantener trazabilidad completa. &
\textbf{Given:} una alerta en estado pendiente.\newline
\textbf{When:} se envía \texttt{PATCH /api/v1/alerts/\{id\}} con un estado válido.\newline
\textbf{Then:} el sistema responde 200, actualiza el estado y conserva el registro original.\newline
\textbf{Given:} un estado no válido.\newline
\textbf{When:} se envía la misma solicitud.\newline
\textbf{Then:} el sistema responde 400 y no modifica la alerta. &
EP-04 \\

\hline

TS-05 &
Observaciones sobre una alerta &
Como Developer, quiero un endpoint que registre observaciones asociadas a una alerta, para dejar trazabilidad de su atención. &
\textbf{Given:} una alerta existente.\newline
\textbf{When:} se envía \texttt{POST /api/v1/alerts/\{id\}/notes} con un texto válido.\newline
\textbf{Then:} el sistema responde 201 y asocia la observación a la alerta. &
EP-04 \\

\hline

TS-06 &
Asociación paciente--proveedor de salud &
Como Developer, quiero un endpoint que asocie un paciente a un proveedor de salud, para vincular la información clínica correspondiente. &
\textbf{Given:} un paciente sin proveedor asociado.\newline
\textbf{When:} se envía \texttt{POST /api/v1/patients/\{id\}/provider} con un proveedor válido.\newline
\textbf{Then:} el sistema responde 200 y vincula al paciente con ese proveedor. &
EP-04 \\

\hline

TS-07 &
Validación de datos mínimos &
Como Developer, quiero que el endpoint de registro de pacientes valide los datos mínimos requeridos, para asegurar información confiable antes de activar el seguimiento. &
\textbf{Given:} una solicitud sin un dato obligatorio.\newline
\textbf{When:} se envía \texttt{POST /api/v1/patients}.\newline
\textbf{Then:} el sistema responde 400 con el listado de campos faltantes.\newline
\textbf{Given:} una solicitud con todos los datos obligatorios.\newline
\textbf{When:} se envía la misma solicitud.\newline
\textbf{Then:} el sistema responde 201 y activa el seguimiento del paciente. &
EP-04 \\

\hline

TS-08 &
Red familiar con roles &
Como Developer, quiero un endpoint que registre múltiples familiares autorizados por adulto mayor con un rol diferenciado, para reflejar cómo se distribuyen las responsabilidades de cuidado. &
\textbf{Given:} un adulto mayor con un familiar principal registrado.\newline
\textbf{When:} se envía \texttt{POST /api/v1/elders/\{id\}/caregivers} con un nuevo familiar y rol secundario.\newline
\textbf{Then:} el sistema responde 201 y autoriza al nuevo familiar sin reemplazar al principal. &
EP-04 \\

\hline

TS-09 &
Registro en modo asistido &
Como Developer, quiero que el endpoint de eventos acepte un origen de captura distinto al del propio adulto mayor, para cubrir los casos donde un cuidador ingresa los datos en su nombre. &
\textbf{Given:} un cuidador autorizado en modo asistido.\newline
\textbf{When:} registra un evento indicando el origen del dato como cuidador.\newline
\textbf{Then:} el sistema persiste el evento distinguiendo su origen. &
EP-04 \\

\hline

TS-10 &
Notificaciones diferenciadas por rol &
Como Developer, quiero un servicio que envíe notificaciones distintas según el rol del destinatario, para que cada uno reciba solo la información relevante. &
\textbf{Given:} una alerta recién creada con destinatarios asociados.\newline
\textbf{When:} el servicio de notificaciones procesa la alerta.\newline
\textbf{Then:} cada destinatario recibe un contenido ajustado a su rol. &
EP-04 \\

\hline

TS-11 &
Control de acceso a datos de salud (RBAC) &
Como Developer, quiero un endpoint que registre el nivel de acceso de cada usuario a los datos de salud de un paciente, para cumplir con las expectativas de privacidad expresadas por los entrevistados. &
\textbf{Given:} un usuario que consulta datos de salud de un paciente.\newline
\textbf{When:} el sistema evalúa su rol.\newline
\textbf{Then:} autoriza o deniega el acceso y registra la decisión en el access-log del paciente. &
EP-04 \\

\hline

\end{longtable}