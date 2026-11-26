## 3.3. Product Backlog

El orden del Product Backlog responde al valor de negocio, no a la conveniencia técnica: las historias de Landing Page se consideran desde el primer sprint, y ninguna historia de seguridad, autenticación o control de acceso se ubica al inicio del backlog; se posicionan una vez que la funcionalidad que protegen ya tiene valor entregado. Las descripciones completas y los criterios de aceptación de cada historia se mantienen únicamente en [3.1. User Stories](31-user-stories.md), de modo que exista una sola fuente de verdad. Las historias de Landing Page (US-01 a US-10, Sprint 1) suman 10 Story Points, coincidiendo con la velocidad planificada para el Sprint 1.

### 3.3.1. Tabla de Backlog

\begingroup
\footnotesize
\setlength{\tabcolsep}{4pt}
\begin{longtable}{|p{0.07\textwidth}|p{0.09\textwidth}|p{0.40\textwidth}|p{0.08\textwidth}|p{0.09\textwidth}|p{0.08\textwidth}|}
\caption{Product Backlog priorizado de VitaLink}\\
\hline
\textbf{Orden} & \textbf{ID} & \textbf{Título} & \textbf{Épica} & \textbf{BG} & \textbf{SP} \\
\hline
\endfirsthead
\hline
\textbf{Orden} & \textbf{ID} & \textbf{Título} & \textbf{Épica} & \textbf{BG} & \textbf{SP} \\
\hline
\endhead

1 & US-01 & Entender la propuesta de valor en segundos & EP-01 & BG-01 & 1 \\ \hline
2 & US-06 & Entender el beneficio sin llamadas constantes & EP-01 & BG-03 & 1 \\ \hline
3 & US-07 & Confiar en quién ve los datos de salud & EP-01 & BG-02 & 1 \\ \hline
4 & US-02 & Confiar antes de registrar datos de pacientes & EP-01 & BG-01 & 1 \\ \hline
5 & US-09 & Entender la plataforma sin tecnicismos & EP-01 & BG-03 & 1 \\ \hline
6 & US-10 & Ver qué esperar antes de registrarse & EP-01 & BG-03 & 1 \\ \hline
7 & US-05 & Ver un ejemplo de cómo funciona una alerta & EP-01 & BG-01 & 1 \\ \hline
8 & US-08 & Conocer cómo funciona antes de crear cuenta & EP-01 & BG-03 & 1 \\ \hline
9 & US-04 & Unirme como proveedor de salud & EP-01 & BG-01 & 1 \\ \hline
10 & US-03 & Solicitar información antes de registrarse & EP-01 & BG-01 & 1 \\ \hline
11 & TS-01 & Ingesta de Telemetría Biométrica & EP-04 & BG-03 & 5 \\ \hline
12 & TS-02 & Listado de alertas & EP-04 & BG-01 \newline BG-03 & 3 \\ \hline
13 & US-18 & Estado general al abrir la app & EP-03 & BG-03 & 2 \\ \hline
14 & US-19 & Recibir una alerta comprensible & EP-03 & BG-03 & 3 \\ \hline
15 & US-20 & Confirmar atención con una acción simple & EP-03 & BG-03 & 2 \\ \hline
16 & US-11 & Resumen inicial de alertas pendientes & EP-02 & BG-01 & 3 \\ \hline
17 & US-12 & Nivel de urgencia diferenciado & EP-02 & BG-01 & 2 \\ \hline
18 & US-15 & Marcar una alerta como revisada o atendida & EP-02 & BG-01 & 3 \\ \hline
19 & TS-04 & Transición de estado de una alerta & EP-04 & BG-01 & 3 \\ \hline
20 & TS-10 & Notificaciones diferenciadas por rol & EP-04 & BG-03 & 5 \\ \hline
21 & US-23 & Evitar duplicar esfuerzos entre familiares & EP-03 & BG-03 & 2 \\ \hline
22 & US-17 & Evitar revisiones duplicadas & EP-02 & BG-01 & 2 \\ \hline
23 & US-13 & Acceder al detalle de un paciente & EP-02 & BG-01 & 2 \\ \hline
24 & US-14 & Historial ordenado por fecha & EP-02 & BG-01 & 3 \\ \hline
25 & TS-03 & Historial Clínico Digital & EP-04 & BG-01 & 3 \\ \hline
26 & US-16 & Agregar una observación a una alerta & EP-02 & BG-01 & 2 \\ \hline
27 & TS-05 & Observaciones sobre una alerta & EP-04 & BG-01 & 2 \\ \hline
28 & US-21 & Historial simple sin preguntar directamente & EP-03 & BG-03 & 3 \\ \hline
29 & US-22 & Ver el dato que originó una alerta & EP-03 & BG-03 & 2 \\ \hline
30 & US-24 & Mantener actualizada la red familiar & EP-03 & BG-03 & 3 \\ \hline
31 & US-26 & Pedir ayuda rápido en una urgencia & EP-03 & BG-03 & 2 \\ \hline
32 & US-25 & Modo de uso extremadamente simple & EP-03 & BG-03 & 5 \\ \hline
33 & TS-09 & Registro en modo asistido & EP-04 & BG-03 & 2 \\ \hline
34 & TS-08 & Red familiar con roles & EP-04 & BG-02 & 3 \\ \hline
35 & TS-06 & Asociación paciente--proveedor de salud & EP-04 & BG-02 & 2 \\ \hline
36 & TS-07 & Validación de datos mínimos & EP-04 & BG-02 & 2 \\ \hline
37 & TS-11 & Control de acceso a datos de salud (RBAC) & EP-04 & BG-02 & 5 \\ \hline

\end{longtable}
\endgroup

**Total:** 37 historias (26 User Stories y 11 Technical Stories) · 86 Story Points. Sprint 1 (US-01 a US-10): 10 Story Points.

### 3.3.2. Tablero público del Backlog

**Herramienta:** Trello  
**URL pública del tablero:** <https://trello.com/b/2CSflHnr>

La captura conserva la estructura histórica del tablero. La URL respondió durante la revisión. El contenido de las tarjetas, su orden vigente y la aceptación por sprint requieren el corte del equipo.

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.8\textheight,keepaspectratio]{assets/ProductBacklog-Trello.png}
\caption{Tablero público del Product Backlog en Trello}
\end{figure}

### 3.3.3. Cobertura técnica para TB2

Se cotejaron las ramas `main` de [Landing Page](https://github.com/CodeBrokers-VitaLink/upc-pre-202620-1asi0729-7737-CodeBrokers-Landin_Page/tree/01adf182c409005f550bc88eafdd055625116dc5), [Frontend](https://github.com/CodeBrokers-VitaLink/upc-pre-202620-1asi0729-7737-CodeBrokers-Frontend/tree/53badd467edd274128be7d89b087023b05e2eccd) y [Backend](https://github.com/CodeBrokers-VitaLink/upc-pre-202620-1asi0729-7737-CodeBrokers-Backend/tree/13db8d940ea800ee84b1956cb3ac7c2c101d8227), junto con el [contrato OpenAPI publicado](https://upc-pre-202620-1asi0729-7737-codebrokers.onrender.com/v3/api-docs). La cobertura se obtuvo por inspección de código y contrato. La aceptación de las historias requiere pruebas y el corte de Sprint 4.

| Historias | Cobertura y brechas observadas |
|---|---|
| US-01, US-02, US-05 a US-10 | `index.html` y `script.js` presentan mensajes, secciones e ilustraciones por audiencia. Comprensión, confianza, claridad de alertas y suficiencia del aviso de privacidad requieren validación. |
| US-03, US-04 | Los CTA llevan al acceso de la aplicación. Desde ahí se puede abrir el registro y elegir médico. La solicitud de información sin cuenta y el ingreso directo al flujo profesional quedan pendientes. |
| US-11 a US-17 | `care-workspace` muestra conteos por estado, prioridad por alerta, búsqueda de pacientes, historial por fecha y seguimiento con notas. Falta verificar la agrupación inicial por severidad y la visibilidad de cambios entre cuentas autorizadas. |
| US-18, US-21, US-22 | El panel familiar muestra estado general, últimas mediciones y resumen semanal. La lista puede mostrar el valor y unidad de la lectura vinculada. Queda pendiente probar la comprensión del contexto completo de cada alerta. |
| US-19, US-20, US-23, US-24, US-25, US-26 | Hay red de cuidado, vista del paciente, notificaciones internas de observaciones y un endpoint de solicitud de ayuda. Siguen pendientes la confirmación familiar de alertas, la gestión completa de contactos y avisos, la validación del modo accesible y el flujo SOS completo con avisos simultáneos. |
| TS-01, TS-02, TS-03 | El alta incorpora mediciones simuladas y Care expone listados de alertas y mediciones por acceso. Los filtros de alerta se aplican en la interfaz. Ingesta de telemetría con generación automática, filtros REST por prioridad y paginación del historial siguen pendientes. |
| TS-04, TS-05, TS-11 | Care e IAM implementan transición con versión, nota de atención e intervención, y control de acceso por sesión, rol y vínculo. Falta ejecutar los escenarios de aceptación de 3.1. |
| TS-06, TS-07, TS-08 | El alta vincula paciente, familiar y médico. Existen relaciones de cuidado y validación de campos, con datos mínimos distintos del criterio histórico de DNI. Sincronizar cuidadores y probar el aislamiento institucional sigue pendiente. |
| TS-09, TS-10 | El código distingue registros iniciales simulados y contempla correo para observaciones médicas. Los criterios de origen manual frente a hardware y de SMS/push diferenciado por rol siguen pendientes. |
