# Capítulo III: Requirements Specification

## 3.1. User Stories

Las User Stories de VitaLink se derivan de las 6 entrevistas registradas ([2.2. Entrevistas](../20-chapter-two/22-entrevistas.md)) para los segmentos Profesionales de Salud y Familiares/Adultos Mayores. Las historias de Landing Page usan como rol base *visitante* (con el subconjunto de segmento cuando aplica), y las Technical Stories (TS) del API RESTful usan el rol *Developer*, describiendo el escenario de interacción request/response en Gherkin.

La cláusula "para…" de cada historia expresa el valor que obtiene el actor. La contribución estratégica se registra de forma explícita en la última columna, mediante el identificador de la épica, del Business Goal (BG) y del Impact (IM) definidos en el [3.2. Impact Mapping](32-impact-mapping.md). Las Technical Stories heredan el BG y el IM de las historias que habilitan, indicadas en su descripción.

\begingroup
\footnotesize
\setlength{\tabcolsep}{4pt}
\begin{longtable}{|p{0.09\textwidth}|p{0.13\textwidth}|p{0.25\textwidth}|p{0.34\textwidth}|p{0.08\textwidth}|}
\caption{User Stories y Technical Stories de VitaLink con trazabilidad a Épica, Business Goal e Impact}\\
\hline
\textbf{ID} & \textbf{Título} & \textbf{Descripción} & \textbf{Criterios de Aceptación} & \textbf{Épica / BG / IM} \\
\hline
\endfirsthead
\hline
\textbf{ID} & \textbf{Título} & \textbf{Descripción} & \textbf{Criterios de Aceptación} & \textbf{Épica / BG / IM} \\
\hline
\endhead

EP-01 & Captación y Confianza (Landing Page) & Comunicar la propuesta de valor de VitaLink a ambos segmentos y convertir visitantes en usuarios registrados. & --- & --- \\ \hline

US-01 & Entender la propuesta de valor en segundos & Como visitante del segmento profesionales de salud, quiero entender en segundos qué problema resuelve VitaLink, para decidir con rapidez si la plataforma merece ser evaluada por mi institución. & \textbf{Given:} un visitante del segmento profesionales de salud ingresa por primera vez al sitio.\newline \textbf{When:} revisa el contenido inicial.\newline \textbf{Then:} identifica el problema que resuelve VitaLink sin necesidad de desplazamiento adicional. & EP-01 \newline BG-01 \newline IM-01 \\ \hline

US-02 & Confiar antes de registrar datos de pacientes & Como visitante del segmento profesionales de salud, quiero conocer las medidas de privacidad y seguridad de datos, para confiar en que la información de mis pacientes estará protegida antes de registrarla. & \textbf{Given:} un visitante del segmento profesionales de salud.\newline \textbf{When:} revisa el contenido de seguridad de la plataforma.\newline \textbf{Then:} encuentra referencias explícitas a cifrado, cumplimiento normativo y control de acceso a los datos. & EP-01 \newline BG-01 \newline IM-01 \\ \hline

US-03 & Solicitar información antes de registrarse & Como visitante del segmento profesionales de salud, quiero solicitar información antes de registrarme, para resolver mis dudas operativas sin comprometer a mi institución. & \textbf{Given:} un visitante del segmento profesionales de salud interesado pero no convencido.\newline \textbf{When:} solicita información de contacto.\newline \textbf{Then:} el sistema registra la solicitud sin exigir la creación de una cuenta médica. & EP-01 \newline BG-01 \newline IM-01 \\ \hline

US-04 & Unirme como proveedor de salud & Como visitante del segmento profesionales de salud, quiero iniciar mi registro como proveedor de forma sencilla, para incorporar a mi institución a la red sin trámites innecesarios. & \textbf{Given:} un visitante del segmento profesionales de salud decidido a afiliarse.\newline \textbf{When:} inicia el registro como proveedor.\newline \textbf{Then:} el sistema lo dirige a un flujo de registro clínico diferenciado del de familiares. & EP-01 \newline BG-01 \newline IM-01 \\ \hline

US-05 & Ver un ejemplo de cómo funciona una alerta & Como visitante del segmento profesionales de salud, quiero conocer un ejemplo de cómo se comunica una alerta, para evaluar cuánto tiempo de interpretación me ahorraría en mi trabajo diario. & \textbf{Given:} un visitante del segmento profesionales de salud.\newline \textbf{When:} revisa el contenido sobre el funcionamiento de las alertas.\newline \textbf{Then:} identifica el nivel de urgencia, el paciente asociado y la acción disponible sin documentación adicional. & EP-01 \newline BG-01 \newline IM-01 \\ \hline

US-06 & Entender el beneficio sin llamadas constantes & Como visitante del segmento familiares, quiero entender en segundos cómo la plataforma me informa del estado de mi familiar, para reducir mi preocupación sin depender de llamadas constantes. & \textbf{Given:} un visitante del segmento familiares ingresa por primera vez al sitio.\newline \textbf{When:} revisa el contenido inicial.\newline \textbf{Then:} identifica el beneficio de monitoreo remoto sin depender de llamadas frecuentes al paciente. & EP-01 \newline BG-03 \newline IM-03 \\ \hline

US-07 & Confiar en quién ve los datos de salud & Como visitante del segmento familiares, quiero conocer quién puede ver los datos de mi familiar, para sentir tranquilidad al registrar información sensible. & \textbf{Given:} un visitante del segmento familiares evaluando registrar a su adulto mayor.\newline \textbf{When:} revisa el contenido de privacidad.\newline \textbf{Then:} encuentra una explicación de qué roles clínicos y familiares acceden a qué datos. & EP-01 \newline BG-02 \newline IM-02 \\ \hline

US-08 & Conocer cómo funciona antes de crear cuenta & Como visitante del segmento familiares, quiero conocer cómo funciona la plataforma antes de crear una cuenta, para decidir registrarme sin entregar datos personales prematuramente. & \textbf{Given:} un visitante del segmento familiares indeciso sobre registrarse.\newline \textbf{When:} revisa el contenido explicativo del funcionamiento.\newline \textbf{Then:} accede a la explicación del flujo Sentir $\rightarrow$ Analizar $\rightarrow$ Actuar sin que se le solicite ningún dato personal. & EP-01 \newline BG-03 \newline IM-03 \\ \hline

US-09 & Entender la plataforma sin tecnicismos & Como visitante del segmento adultos mayores, quiero entender en lenguaje simple qué hace la plataforma, para aceptar su uso sin sentirme abrumado por la tecnología. & \textbf{Given:} un visitante del segmento adultos mayores con baja familiaridad tecnológica.\newline \textbf{When:} revisa el mensaje principal del sitio.\newline \textbf{Then:} el contenido evita jerga médica o técnica y comunica el beneficio de acompañamiento. & EP-01 \newline BG-03 \newline IM-03 \\ \hline

US-10 & Ver qué esperar antes de registrarse & Como visitante del segmento familiares, quiero ver una representación del panel de control, para saber qué producto usaré antes de crear mi cuenta. & \textbf{Given:} un visitante del segmento familiares.\newline \textbf{When:} revisa el contenido que ilustra el panel de control.\newline \textbf{Then:} visualiza una representación del dashboard familiar antes de crear una cuenta. & EP-01 \newline BG-03 \newline IM-03 \\ \hline

EP-02 & Monitoreo Clínico y Gestión de Alertas & Dar a los profesionales de salud una vista operativa de sus pacientes y del ciclo de vida de cada alerta. & --- & --- \\ \hline

US-11 & Resumen inicial de alertas pendientes & Como médico, quiero un resumen con la cantidad de alertas pendientes, para priorizar mi atención al iniciar la jornada. & \textbf{Given:} un médico con sesión iniciada.\newline \textbf{When:} accede al panel principal.\newline \textbf{Then:} el sistema presenta la cantidad de alertas pendientes agrupadas por severidad. & EP-02 \newline BG-01 \newline IM-04 \\ \hline

US-12 & Nivel de urgencia diferenciado & Como médico, quiero identificar visualmente el nivel de urgencia de cada alerta, para decidir rápidamente cuál revisar primero. & \textbf{Given:} una lista de alertas del médico.\newline \textbf{When:} revisa cada alerta.\newline \textbf{Then:} cada una indica su nivel de urgencia sin requerir abrir el detalle. & EP-02 \newline BG-01 \newline IM-04 \\ \hline

US-13 & Acceder al detalle de un paciente & Como médico, quiero acceder al detalle de un paciente desde una alerta, para revisar su contexto clínico y decidir con información suficiente. & \textbf{Given:} una alerta asociada a un paciente.\newline \textbf{When:} el médico selecciona esa alerta.\newline \textbf{Then:} el sistema presenta el detalle biométrico del paciente asociado. & EP-02 \newline BG-01 \newline IM-04 \\ \hline

US-14 & Historial ordenado por fecha & Como médico, quiero consultar el historial de un paciente ordenado por fecha, para identificar patrones de salud a lo largo del tiempo. & \textbf{Given:} el detalle de un paciente con registros previos.\newline \textbf{When:} el médico consulta su historial.\newline \textbf{Then:} los registros se presentan en orden cronológico descendente. & EP-02 \newline BG-01 \newline IM-04 \\ \hline

US-15 & Marcar una alerta como revisada o atendida & Como médico, quiero cambiar el estado de una alerta a ``en revisión'' o ``atendida'', para coordinarme con el equipo clínico y evitar atenciones duplicadas. & \textbf{Given:} una alerta en estado pendiente.\newline \textbf{When:} el médico marca la alerta como ``en revisión''.\newline \textbf{Then:} el sistema actualiza el estado de forma visible para todos los usuarios con acceso. & EP-02 \newline BG-01 \newline IM-04 \\ \hline

US-16 & Agregar una observación a una alerta & Como médico, quiero registrar una observación breve al atender una alerta, para dejar constancia clínica auditable de la acción tomada. & \textbf{Given:} una alerta que el médico acaba de atender.\newline \textbf{When:} registra una observación.\newline \textbf{Then:} la nota clínica queda asociada de forma inmutable al historial de la alerta. & EP-02 \newline BG-01 \newline IM-04 \\ \hline

US-17 & Evitar revisiones duplicadas & Como médico, quiero saber si un caso ya fue revisado por otro colega, para no duplicar esfuerzo y dedicar mi tiempo a otros casos. & \textbf{Given:} una alerta ya marcada ``en revisión'' por otro profesional.\newline \textbf{When:} el médico accede a esa alerta.\newline \textbf{Then:} el sistema indica el nombre del profesional que la está revisando. & EP-02 \newline BG-01 \newline IM-04 \\ \hline

EP-03 & Acompañamiento Familiar y Autocuidado & Permitir que familiares y adultos mayores sigan el estado de salud y actúen ante una alerta. & --- & --- \\ \hline

US-18 & Estado general al abrir la app & Como familiar, quiero ver un estado general simple al abrir la app, para saber de inmediato si debo intervenir sin interpretar números. & \textbf{Given:} un usuario familiar con sesión iniciada.\newline \textbf{When:} abre la aplicación.\newline \textbf{Then:} el sistema presenta un indicador macro de estado (ej. ``Estable'') sin requerir interpretar valores crudos. & EP-03 \newline BG-03 \newline IM-03 \\ \hline

US-19 & Recibir una alerta comprensible & Como familiar, quiero recibir una alerta clara que indique la gravedad, para decidir rápidamente cómo actuar. & \textbf{Given:} un evento fuera de la línea base del adulto mayor.\newline \textbf{When:} el sistema genera la alerta.\newline \textbf{Then:} el destinatario recibe una notificación push o SMS indicando gravedad y sugerencia de acción. & EP-03 \newline BG-03 \newline IM-03 \\ \hline

US-20 & Confirmar atención con una acción simple & Como familiar, quiero confirmar rápidamente que ya atendí una situación, para que el resto de la red de cuidado sepa que está cubierta. & \textbf{Given:} una alerta activa.\newline \textbf{When:} el usuario confirma la atención.\newline \textbf{Then:} el sistema marca la alerta como ``Acompañada'' y notifica al resto de la red. & EP-03 \newline BG-03 \newline IM-03 \\ \hline

US-21 & Historial simple sin preguntar directamente & Como familiar, quiero consultar un historial simplificado de días anteriores, para observar tendencias de bienestar sin interrogar al adulto mayor y preservar su independencia. & \textbf{Given:} un usuario en la vista de historial.\newline \textbf{When:} selecciona la última semana.\newline \textbf{Then:} el sistema presenta un resumen de normalidad biométrica sin detalles técnicos complejos. & EP-03 \newline BG-03 \newline IM-03 \\ \hline

US-22 & Ver el dato que originó una alerta & Como familiar, quiero conocer el dato biométrico que originó la alerta, para informar con precisión al centro médico si decido llamar a emergencias. & \textbf{Given:} una alerta médica abierta.\newline \textbf{When:} el familiar consulta su detalle.\newline \textbf{Then:} el sistema muestra el valor, el rango esperado y la hora exacta del suceso. & EP-03 \newline BG-03 \newline IM-03 \\ \hline

US-23 & Evitar duplicar esfuerzos entre familiares & Como familiar, quiero saber si otro familiar ya atendió una alerta, para evitar llamadas repetidas que saturen al adulto mayor. & \textbf{Given:} una alerta ya atendida por un hermano.\newline \textbf{When:} el usuario consulta la alerta.\newline \textbf{Then:} el sistema indica el nombre del familiar que cerró el incidente. & EP-03 \newline BG-03 \newline IM-03 \\ \hline

US-24 & Mantener actualizada la red familiar & Como familiar, quiero actualizar mis datos y la red de cuidado, para que las notificaciones de urgencia lleguen siempre a la persona correcta. & \textbf{Given:} un usuario en la vista de red de cuidado.\newline \textbf{When:} modifica el teléfono del contacto principal.\newline \textbf{Then:} el sistema guarda los cambios y actualiza el enrutamiento de notificaciones. & EP-03 \newline BG-03 \newline IM-03 \\ \hline

US-25 & Modo de uso extremadamente simple & Como adulto mayor, quiero operar la aplicación con el mínimo de pasos posible, para mantener mi autonomía sin depender de asistencia técnica. & \textbf{Given:} un adulto mayor operando la aplicación.\newline \textbf{When:} desea ver su propio estado.\newline \textbf{Then:} la pantalla principal utiliza contraste alto y botones grandes sin menús ocultos. & EP-03 \newline BG-03 \newline IM-03 \\ \hline

US-26 & Pedir ayuda rápido en una urgencia & Como adulto mayor, quiero un botón de pánico virtual, para pedir ayuda inmediata sin tener que explicar mi situación. & \textbf{Given:} un adulto mayor con la app abierta.\newline \textbf{When:} presiona el botón de SOS.\newline \textbf{Then:} el sistema genera una alerta de prioridad crítica (Prioridad 1) y notifica a médicos y familiares simultáneamente. & EP-03 \newline BG-03 \newline IM-03 \\ \hline

EP-04 & Plataforma de Datos y Alertas (API) & Sostener con datos confiables y trazables el flujo Sentir $\rightarrow$ Analizar $\rightarrow$ Actuar entre wearables, backend e IA. & --- & --- \\ \hline

TS-01 & Ingesta de Telemetría Biométrica & Como Developer, quiero un endpoint que reciba Telemetría Biométrica y genere una alerta automáticamente cuando el valor se desvíe de la Línea Base, para automatizar el triaje clínico. Habilita: US-18, US-19, US-22. & \textbf{Given:} un payload válido con frecuencia cardíaca.\newline \textbf{When:} se envía \texttt{POST /api/v1/telemetry}.\newline \textbf{Then:} el sistema responde 201 y, si hay desviación, crea un registro en la tabla de alertas. & EP-04 \newline BG-03 \newline IM-03 \\ \hline

TS-02 & Listado de alertas & Como Developer, quiero un endpoint que liste alertas filtrables por estado y prioridad, para proveer datos a las vistas de médicos y familiares de forma eficiente. Habilita: US-11, US-12, US-18. & \textbf{Given:} alertas existentes.\newline \textbf{When:} se envía \texttt{GET /api/v1/alerts?status=PENDING}.\newline \textbf{Then:} el sistema responde 200 con el arreglo JSON de alertas ordenadas por prioridad. & EP-04 \newline BG-01 \newline BG-03 \newline IM-03/04 \\ \hline

TS-03 & Historial Clínico Digital & Como Developer, quiero un endpoint que exponga el Historial Clínico de un paciente, para poblar los gráficos de tendencia del frontend. Habilita: US-14, US-21. & \textbf{Given:} un paciente con mediciones previas.\newline \textbf{When:} se envía \texttt{GET /api/v1/patients/\{id\}/history}.\newline \textbf{Then:} el sistema responde 200 con los registros paginados cronológicamente. & EP-04 \newline BG-01 \newline IM-04 \\ \hline

TS-04 & Transición de estado de una alerta & Como Developer, quiero un endpoint que cambie el estado de una alerta sin borrarla, para mantener la inmutabilidad y la auditoría de los eventos clínicos. Habilita: US-15, US-17, US-20, US-23. & \textbf{Given:} una alerta en estado PENDING.\newline \textbf{When:} se envía \texttt{PATCH /api/v1/alerts/\{id\}} con el cuerpo \texttt{\{status: REVIEW\}}.\newline \textbf{Then:} el sistema responde 200 y registra el timestamp del cambio. & EP-04 \newline BG-01 \newline IM-04 \\ \hline

TS-05 & Observaciones sobre una alerta & Como Developer, quiero un endpoint para adjuntar notas a una alerta, para soportar la trazabilidad de la decisión médica tomada. Habilita: US-16. & \textbf{Given:} una alerta válida.\newline \textbf{When:} se envía \texttt{POST /api/v1/alerts/\{id\}/notes}.\newline \textbf{Then:} el sistema responde 201 y la nota queda asociada de forma inmutable al evento. & EP-04 \newline BG-01 \newline IM-04 \\ \hline

TS-06 & Asociación paciente--proveedor de salud & Como Developer, quiero un endpoint que asocie un paciente a un centro médico, para aislar correctamente los datos (Tenant Isolation) por clínica. Habilita: US-11, US-13. & \textbf{Given:} un UUID de paciente y uno de clínica.\newline \textbf{When:} se envía \texttt{POST /api/v1/patients/\{id\}/affiliations}.\newline \textbf{Then:} el sistema responde 200 y actualiza la relación en la base de datos. & EP-04 \newline BG-02 \newline IM-02 \\ \hline

TS-07 & Validación de datos mínimos & Como Developer, quiero validar en el backend los esquemas de creación de pacientes, para prevenir corrupción de datos y fallos en el motor de alertas. Habilita: TS-01. & \textbf{Given:} un payload sin DNI.\newline \textbf{When:} se envía \texttt{POST /api/v1/patients}.\newline \textbf{Then:} el sistema rechaza la petición con HTTP 400 Bad Request y un arreglo de errores de validación. & EP-04 \newline BG-02 \newline IM-02 \\ \hline

TS-08 & Red familiar con roles & Como Developer, quiero un endpoint que gestione los cuidadores de cada paciente, para reflejar correctamente el esquema RBAC de acceso de las familias. Habilita: US-24. & \textbf{Given:} un arreglo de IDs de familiares.\newline \textbf{When:} se envía \texttt{PUT /api/v1/patients/\{id\}/caregivers}.\newline \textbf{Then:} el sistema sincroniza las relaciones de acceso en la tabla correspondiente. & EP-04 \newline BG-02 \newline IM-02 \\ \hline

TS-09 & Registro en modo asistido & Como Developer, quiero soportar un indicador \texttt{origin} en las peticiones de signos vitales, para diferenciar las métricas capturadas por hardware de las ingresadas manualmente por el cuidador. Habilita: US-25. & \textbf{Given:} un registro manual enviado por el familiar.\newline \textbf{When:} se procesa el evento.\newline \textbf{Then:} el sistema lo marca como modo asistido, asegurando la transparencia de la fuente. & EP-04 \newline BG-03 \newline IM-03 \\ \hline

TS-10 & Notificaciones diferenciadas por rol & Como Developer, quiero un worker o bus de eventos que envíe notificaciones variando el contenido según el destinatario, para desacoplar el motor de alertas de la capa de comunicación. Habilita: US-19, US-26. & \textbf{Given:} un evento de alerta crítica.\newline \textbf{When:} el sistema enruta las notificaciones.\newline \textbf{Then:} el SMS al familiar usa una plantilla distinta a la notificación push del médico. & EP-04 \newline BG-03 \newline IM-03 \\ \hline

TS-11 & Control de acceso a datos de salud (RBAC) & Como Developer, quiero validar JWT y roles en cada endpoint, para garantizar que ningún usuario exceda los permisos de visualización estipulados por las normativas HIPAA/GDPR. Habilita: US-02, US-07, US-13. & \textbf{Given:} una petición a un recurso de un paciente no afiliado al médico en sesión.\newline \textbf{When:} el API Gateway evalúa el token JWT.\newline \textbf{Then:} el sistema responde HTTP 403 Forbidden e impide el acceso a los datos. & EP-04 \newline BG-02 \newline IM-02 \\ \hline

\end{longtable}
\endgroup