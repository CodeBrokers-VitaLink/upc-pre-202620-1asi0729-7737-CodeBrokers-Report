## 5.2. Landing Page, Services & Applications Implementation

### 5.2.1. Sprint 1

Durante el Sprint 1, el equipo CodeBrokers se enfocó en desarrollar la primera versión funcional de la Landing Page de VitaLink y su integración inicial con el frontend en Angular.

El objetivo principal fue comunicar la propuesta de valor del producto, mostrando cómo VitaLink permite realizar un monitoreo preventivo del adulto mayor mediante alertas inteligentes y facilitar la comunicación entre familiares y profesionales de salud.

Durante este Sprint se desarrollaron las primeras secciones visuales del producto, aplicando los criterios definidos durante la etapa de diseño UX/UI y preparando la primera versión desplegada de la Landing Page en un entorno público.

#### 5.2.1.1. Sprint Planning 1

Durante el Sprint Planning 1, el equipo definió como objetivo principal desarrollar y desplegar la primera versión funcional de la Landing Page de VitaLink. Para ello, se seleccionaron las User Stories US-01 a US-10 de la épica EP-01 Captación y Confianza, que suman **10 Story Points**, igual a la velocidad definida para el inicio del proyecto.

*Criterio de estimación.* El Product Backlog revisado asigna 1 Story Point a cada historia US-01 a US-10, para un alcance de 10 SP. Los Story Points expresan complejidad relativa; no equivalen a horas ni prueban aceptación. Las tareas T01 a T10 estiman 29 horas y las habilitadoras T11 a T15, 14 horas adicionales: 43 horas en total. La corrección del backlog realizada el 6 de octubre y esta reconciliación se registran en el historial de versiones.

\begingroup
\footnotesize
\begin{longtable}{|p{0.26\textwidth}|p{0.64\textwidth}|}
\caption{Sprint Planning 1}\\
\hline
\textbf{Sprint \#} & \textbf{Sprint 1} \\ \hline
\endhead
\textbf{Sprint Planning Background} & \\ \hline
\textbf{Date} & 2026-09-01 \\ \hline
\textbf{Time} & 7:00 PM \\ \hline
\textbf{Location} & Reunión virtual mediante Discord \\ \hline
\textbf{Prepared By} & Deiby Vargas \\ \hline
\textbf{Attendees (to planning meeting)} & Fernando Contreras, Pablo Martinez, Yazid Said, Kirk Quiliano, Deiby Vargas \\ \hline
\textbf{Sprint 0 Review Summary} & Al tratarse del primer Sprint del proyecto, no existe un Sprint anterior para realizar una revisión de resultados. El equipo inicia tomando como base los artefactos desarrollados durante Requirements Elicitation, Requirements Specification y Product Design. \\ \hline
\textbf{Sprint 0 Retrospective Summary} & Al no existir un Sprint previo, no se cuenta con una retrospectiva anterior. Como punto inicial, el equipo acordó utilizar GitFlow para el trabajo colaborativo, Trello para el seguimiento de tareas y GitHub para el control de versiones y la revisión de cambios. \\ \hline
\textbf{Sprint Goal \& User Stories} & \\ \hline
\textbf{Sprint 1 Goal} & Nuestro enfoque está en desarrollar y publicar una primera versión funcional, responsive y accesible de la Landing Page de VitaLink. Creemos que esto permitirá que profesionales de salud, familiares y adultos mayores comprendan la propuesta de valor del producto. Esto se confirmará cuando la Landing Page se encuentre desplegada públicamente e incluya las funcionalidades definidas en las User Stories US-01 a US-10 de la épica EP-01. \\ \hline
\textbf{Sprint 1 Velocity} & 10 Story Points \\ \hline
\textbf{Sum of Story Points} & 10 Story Points (US-01 a US-10) \\ \hline
\end{longtable}
\endgroup

#### 5.2.1.2. Aspect Leaders and Collaborators

Durante el Sprint 1 se definieron los principales aspectos del desarrollo de la primera versión funcional de la Landing Page de VitaLink. Para cada aspecto se asignó un integrante como **Leader (L)**, responsable principal de dirigir y supervisar su desarrollo, mientras que los demás participaron como **Collaborators (C)**.

\begingroup
\footnotesize
\setlength{\tabcolsep}{3pt}
\begin{longtable}{|p{0.15\textwidth}|p{0.13\textwidth}|p{0.13\textwidth}|p{0.14\textwidth}|p{0.11\textwidth}|p{0.12\textwidth}|p{0.13\textwidth}|}
\caption{Aspect Leaders and Collaborators del Sprint 1}\\
\hline
\textbf{Team Member} & \textbf{GitHub Username} & \textbf{Structure \& Hero} & \textbf{Benefits, Alerts \& Privacy} & \textbf{Responsive UI} & \textbf{Sprint Docs} & \textbf{Deployment \& Integration} \\ \hline
\endhead
Fernando Contreras & FernSkibidi69 & C & C & C & & C \\ \hline
Pablo Martinez & Delzekl & C & C & C & C & \\ \hline
Yazid Said & BL4Z3K4D & L & L & L & & C \\ \hline
Kirk Quiliano & Kirkcito & & C & & L & C \\ \hline
Deiby Vargas & poluxbinPe & C & & C & C & L \\ \hline
\end{longtable}
\endgroup

**L:** Leader | **C:** Collaborator

#### 5.2.1.3. Sprint Backlog 1

La revisión del 8 de octubre de 2026 contrasta T01 a T15 con los criterios de las historias, la landing publicada, su código y el tablero público. Las tareas T01 a T10 desarrollan la User Story indicada; T11 a T15 son habilitadoras del Sprint Goal. Se conservan responsables y horas de la planificación; estos campos no prueban autoría de commits ni aceptación.

**Estados de esta revisión:** Done indica un criterio observable o artefacto comprobado; To-review, evidencia parcial o una revisión pendiente; To-do, un criterio que la publicación consultada no cumple. El resultado es 6 Done, 5 To-review y 4 To-do. Esta verificación no reemplaza un acta de aceptación ni modifica el tablero.

El tablero contiene 8 tarjetas en DONE, sin identificadores T01–T15 ni checklists que permitan confirmar una correspondencia completa. Su estado no acredita automáticamente las 15 tareas del informe. En particular, la tarjeta de formulario de contacto está en DONE, pero la publicación revisada no contiene un formulario que registre solicitudes. El responsable del tablero debe vincular cada tarea con su evidencia y conciliar estos resultados antes de declarar el Sprint totalmente cerrado.

**Sprint Board:** Trello  
**URL pública:** <https://trello.com/b/uWEShiCR/sprint-codebrokers>

\begin{figure}[H]
\centering
\includegraphics[width=\linewidth,height=0.8\textheight,keepaspectratio]{assets/SprintBoard-Trello.jpg}
\caption{Captura real del Sprint Board, 8 de octubre de 2026: 8 tarjetas en DONE, sin IDs de las 15 tareas}
\end{figure}

\begin{landscape}
\begingroup
\small
\setlength{\tabcolsep}{4pt}
\begin{longtable}{|p{0.05\textwidth}|p{0.05\textwidth}|p{0.16\textwidth}|p{0.045\textwidth}|p{0.12\textwidth}|p{0.27\textwidth}|p{0.05\textwidth}|p{0.07\textwidth}|p{0.05\textwidth}|}
\caption{Sprint Backlog 1}\\
\hline
\textbf{Sprint \#} & \textbf{Story Id} & \textbf{Story Title} & \textbf{Task Id} & \textbf{Task Title} & \textbf{Task Description} & \textbf{Est. (h)} & \textbf{Assigned To} & \textbf{Status} \\ \hline
\endfirsthead
\hline
\textbf{Sprint \#} & \textbf{Story Id} & \textbf{Story Title} & \textbf{Task Id} & \textbf{Task Title} & \textbf{Task Description} & \textbf{Est. (h)} & \textbf{Assigned To} & \textbf{Status} \\ \hline
\endhead

1 & US-01 & Entender la propuesta de valor en segundos & T01 & Implement Hero section & Implementar la sección inicial mostrando la propuesta de valor. & 3 & Yazid Said & \textbf{Done} \\ \hline
1 & US-02 & Confiar antes de registrar datos de pacientes & T02 & Implement security section & Contenido sobre cifrado y privacidad de datos. & 3 & Pablo Martinez & \textbf{Done} \\ \hline
1 & US-03 & Solicitar información antes de registrarse & T03 & Implement contact section & Formulario para solicitar información corporativa. & 3 & Fernando Contreras & \textbf{To-do} \\ \hline
1 & US-04 & Unirme como proveedor de salud & T04 & Implement healthcare CTA & Call to Action para el registro clínico de proveedores. & 3 & Yazid Said & \textbf{To-do} \\ \hline
1 & US-05 & Ver un ejemplo de cómo funciona una alerta & T05 & Implement alert example & Diseño visual simulado de una alerta y su paciente. & 3 & Pablo Martinez & \textbf{To-do} \\ \hline
1 & US-06 & Entender el beneficio sin llamadas constantes & T06 & Implement family benefits & Sección sobre el monitoreo remoto automático. & 3 & Fernando Contreras & \textbf{Done} \\ \hline
1 & US-07 & Confiar en quién ve los datos de salud & T07 & Implement family privacy & Explicación de acceso por roles y visibilidad de los datos de salud. & 3 & Pablo Martinez & \textbf{To-review} \\ \hline
1 & US-08 & Conocer cómo funciona antes de crear cuenta & T08 & Implement how-it-works & Sección explicativa de los pasos de captura de datos. & 3 & Yazid Said & \textbf{Done} \\ \hline
1 & US-09 & Entender la plataforma sin tecnicismos & T09 & Adapt content & Redacción de textos en lenguaje accesible. & 2 & Kirk Quiliano & \textbf{To-review} \\ \hline
1 & US-10 & Ver qué esperar antes de registrarse & T10 & Implement dashboard preview & Imágenes previas de las interfaces familiares. & 3 & Yazid Said & \textbf{To-do} \\ \hline
1 & US-01 a US-10 (transversal) & Habilitadora & T11 & Responsive design & CSS y Media Queries para dispositivos móviles. & 4 & Fernando Contreras & \textbf{To-review} \\ \hline
1 & US-01 a US-10 (transversal) & Habilitadora & T12 & Review UX/UI consistency & Verificación WCAG y coherencia con Figma. & 3 & Pablo Martinez & \textbf{To-review} \\ \hline
1 & Sprint Goal & Habilitadora & T13 & Review Sprint docs & Actualización del reporte en Markdown. & 2 & Kirk Quiliano & \textbf{To-review} \\ \hline
1 & US-01 a US-10 (transversal) & Habilitadora & T14 & Integrate Landing & Resolución de conflictos de merge en Git e integración de ramas. & 3 & Deiby Vargas & \textbf{Done} \\ \hline
1 & Sprint Goal & Habilitadora & T15 & Deploy Landing Page & Configuración de GitHub Pages y Actions. & 2 & Deiby Vargas & \textbf{Done} \\ \hline

\end{longtable}
\endgroup
\end{landscape}


**Verificación por tarea y criterio de cierre**

La publicación consultada corresponde a `main`, commit `91ffa24f1bff259a36e2158be5d98385a41bd972`, del repositorio de la Landing Page. Las evidencias registran ese corte; una modificación posterior requiere repetir la comprobación.

| Task / historia | Criterio contrastado y resultado observable | Evidencia |
|---|---|---|
| T01 / US-01 | El Hero clínico comunica el problema y la propuesta de valor en el contenido inicial. Done. | E-01, E-02 |
| T02 / US-02 | La sección de seguridad menciona cifrado, normativa y RBAC. Done para el criterio de contenido; no certifica seguridad implementada ni cumplimiento legal. | E-01 |
| T03 / US-03 | Solicitar información debe registrar una solicitud sin cuenta. El CTA apunta a `#ventajas-clinicas`; se observaron 0 formularios y 0 campos de contacto. To-do. | E-01, E-04; tarjeta E-06 |
| T04 / US-04 | El CTA debe abrir un registro clínico diferenciado. Los enlaces llevan a secciones locales como `#unirse` o `#planes`; no se comprobó ese flujo. To-do. | E-01, E-04 |
| T05 / US-05 | El ejemplo debe identificar urgencia, paciente y acción. La sección usa una foto de una profesional con una tableta; no muestra un ejemplo de alerta legible con esos tres elementos. To-do. | E-01, E-09 |
| T06 / US-06 | El Hero familiar explica monitoreo remoto y tranquilidad sin llamadas constantes. Done. | E-01, E-03 |
| T07 / US-07 | Debe indicar qué roles clínicos/familiares acceden a qué datos. El texto genérico de RBAC menciona roles, pero no detalla la correspondencia rol–dato. To-review. | E-01 |
| T08 / US-08 | El contenido familiar explica sensor, análisis, alerta y estado compartido antes de crear una cuenta y sin pedir datos personales. Done. | E-01, E-04 |
| T09 / US-09 | El mensaje debe comunicar acompañamiento sin jerga para adultos mayores. La vista familiar comunica el beneficio, pero conserva textos como «Telemetría Continua»; falta cerrar la revisión de lenguaje. To-review. | E-01, E-05 |
| T10 / US-10 | Debe verse una representación del dashboard familiar. La imagen de monitoreo familiar es la misma fotografía y no acredita ese panel. To-do. | E-01, E-09 |
| T11 / transversal | Existen media queries. A 375 × 812 el menú abre y no se detectó desbordamiento horizontal del documento, pero el selector Familiares queda recortado. To-review. | E-01, E-05 |
| T12 / transversal | Debe comprobarse coherencia con Figma y accesibilidad. La captura y la presencia de atributos ARIA no bastan para acreditar la revisión WCAG completa. To-review. | E-01, E-05 |
| T13 / Sprint Goal | El informe incorpora puntos y evidencias corregidos; aún requiere revisión de la atribución individual y de la exportación final. To-review. | Secciones 5.2.1.3 y 5.2.1.4 |
| T14 / transversal | La landing está integrada en `main` mediante PR #6, commit `91ffa24`. Done para el artefacto de integración; la atribución individual se verifica aparte. | E-07 |
| T15 / Sprint Goal | GitHub Pages publica la landing; el workflow del commit `91ffa24` finalizó correctamente y la URL abre. Done. | E-04, E-08 |

**Fuentes verificables del Sprint 1**

| ID | Fuente |
|---|---|
| E-01 | [Código de la landing en el commit verificado](https://github.com/CodeBrokers-VitaLink/upc-pre-202620-1asi0729-7737-CodeBrokers-Landin_Page/tree/91ffa24f1bff259a36e2158be5d98385a41bd972) |
| E-02 | [Captura de escritorio, segmento clínico](../../assets/Sprint1-Landing-Desktop.jpg) |
| E-03 | [Captura del segmento familiar](../../assets/Sprint1-Landing-Family.jpg) |
| E-04 | [Observación de formularios y CTA](../../assets/evidence/sprint-1-landing-observation.json) y [landing publicada](https://codebrokers-vitalink.github.io/upc-pre-202620-1asi0729-7737-CodeBrokers-Landin_Page/) |
| E-05 | [Captura móvil](../../assets/Sprint1-Landing-Mobile.jpg) y [resultado de la comprobación](../../assets/evidence/sprint-1-mobile-observation.json) |
| E-06 | [Captura real de Trello](../../assets/SprintBoard-Trello.jpg), [listado observado de sus 8 tarjetas](../../assets/evidence/sprint-1-board-observation.json) y [tarjeta de contacto](https://trello.com/c/EDWpN9ZY) |
| E-07 | [PR #6 de integración de la landing](https://github.com/CodeBrokers-VitaLink/upc-pre-202620-1asi0729-7737-CodeBrokers-Landin_Page/pull/6) |
| E-08 | [Workflow exitoso de GitHub Pages](https://github.com/CodeBrokers-VitaLink/upc-pre-202620-1asi0729-7737-CodeBrokers-Landin_Page/actions/runs/34932280482) |
| E-09 | [Imagen utilizada en alertas y monitoreo familiar](https://github.com/CodeBrokers-VitaLink/upc-pre-202620-1asi0729-7737-CodeBrokers-Landin_Page/blob/91ffa24f1bff259a36e2158be5d98385a41bd972/assets/screen.png) |

#### 5.2.1.4. Development Evidence for Sprint Review

La siguiente matriz conserva las referencias de atribución individual del borrador para su contraste. Sus asociaciones entre integrantes, tareas y commits aún requieren revisión; no se utilizan como prueba de aceptación. Los criterios y artefactos comprobados se registran en 5.2.1.3.

**Ruta de trazabilidad:** Integrante $\rightarrow$ Branch $\rightarrow$ Commit / Pull Request $\rightarrow$ Task / US $\rightarrow$ Resultado.

\begin{landscape}
\begingroup
\small
\setlength{\tabcolsep}{4pt}
\begin{longtable}{|p{0.11\textwidth}|p{0.16\textwidth}|p{0.14\textwidth}|p{0.07\textwidth}|p{0.09\textwidth}|p{0.30\textwidth}|}
\caption{Referencias previas de atribución individual del Sprint 1, pendientes de conciliación}\\
\hline
\textbf{Integrante} & \textbf{Branch (GitFlow)} & \textbf{Commit / PR} & \textbf{Task} & \textbf{US} & \textbf{Resultado} \\ \hline
\endfirsthead
\hline
\textbf{Integrante} & \textbf{Branch (GitFlow)} & \textbf{Commit / PR} & \textbf{Task} & \textbf{US} & \textbf{Resultado} \\ \hline
\endhead

Yazid Said & \texttt{develop} & PR \#6 / \texttt{91ffa24} & T01 & US-01 & Integración de componentes y propuesta de valor en la rama develop. \\ \hline
Yazid Said & \texttt{feature/footer} & PR \#5 / \texttt{abf9be7} & T08 & US-08 & Estructura del footer, enlaces informativos y cómo funciona. \\ \hline
Yazid Said & \texttt{chore/logo} & Commit \texttt{389e581} & T04 & US-04 & Adición del logotipo oficial y assets base del CTA institucional. \\ \hline
Pablo Martinez & \texttt{feat/navbar-hero} & PR \#1 / \texttt{db20de2} & T02 \newline T05 & US-02 \newline US-05 & Barra de navegación, Hero section y estructura base de seguridad y alertas. \\ \hline
Pablo Martinez & \texttt{feat/navbar-hero} & Commit \texttt{d55fc4a} & T07 \newline T12 & US-07 \newline - & Navegación a secciones de privacidad, consistencia UX/UI y accesibilidad. \\ \hline
Fernando Contreras & \texttt{feat/pricing} & Commit \texttt{baae70f} & T03 \newline T06 & US-03 \newline US-06 & Secciones institucionales, pricing tiers, testimonios y beneficios familiares. \\ \hline
Fernando Contreras & \texttt{feat/pricing} & Commit \texttt{bcbcc2d} & T11 & - & Ajustes CSS, testimonios y Media Queries para dispositivos móviles. \\ \hline
Kirk Quiliano & \texttt{docs/report} & Commit \texttt{15b22e8} & T09 \newline T13 & US-09 \newline - & Textos revisados en lenguaje accesible y actualización del repositorio del informe. \\ \hline
Deiby Vargas & \texttt{main} & PR \#32 / \texttt{f2d7652} & T14 \newline T15 & - & Orquestación de ramas, resolución de conflictos en Git y despliegue final. \\ \hline

\end{longtable}
\endgroup
\end{landscape}

La atribución debe contrastar cada hash y PR con su repositorio, autor y diff. El PR #6 y el workflow de E-07/E-08 pertenecen a la Landing Page; un commit del Report no demuestra por sí solo implementación o despliegue de esa landing. Las referencias pendientes no se contabilizan como aportes individuales aceptados.

#### 5.2.1.5. Execution Evidence for Sprint Review

La observación del 8 de octubre de 2026 comprobó la landing publicada del commit `91ffa24`: contenido inicial de ambos segmentos, explicación familiar sin registro previo y disponibilidad pública del sitio. Los resultados por historia están en 5.2.1.3, junto con los criterios pendientes. No se declara que las 15 tareas estén aceptadas.

En la vista móvil de 375 × 812 se comprobó la apertura del menú y se registró un recorte del selector de segmento. Esa comprobación no equivale a una auditoría completa de accesibilidad o de todos los dispositivos.

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.75\textheight,keepaspectratio]{assets/Sprint1-Landing-Desktop.jpg}
\caption{Observación de la landing publicada: Hero clínico, 8 de octubre de 2026}
\end{figure}

\begin{figure}[htbp]
\centering
\includegraphics[width=\linewidth,height=0.75\textheight,keepaspectratio]{assets/Sprint1-Landing-Family.jpg}
\caption{Observación de la landing publicada: Hero familiar, 8 de octubre de 2026}
\end{figure}

\begin{figure}[htbp]
\centering
\includegraphics[width=0.45\linewidth,height=0.75\textheight,keepaspectratio]{assets/Sprint1-Landing-Mobile.jpg}
\caption{Comprobación a 375 por 812 píxeles: el selector Familiares queda recortado}
\end{figure}

Las capturas previas siguientes se conservan como evidencia visual del contenido; su presencia no reemplaza la comprobación de criterios ni acredita funcionalidades ausentes.

**Medicos**


-Incios:


<img width="900" alt="image" src="https://github.com/user-attachments/assets/de26183e-d214-43eb-855c-34bb1142a822" />


Descripción:

<img width="900" alt="image" src="https://github.com/user-attachments/assets/6103073c-4e08-4406-90af-3be5dbcab3c8" />


Pagos:


<img width="900" alt="image" src="https://github.com/user-attachments/assets/b01dfa62-8047-4ee8-b642-b126f6cc40e0" />


- Seguridad:


<img width="900" alt="image" src="https://github.com/user-attachments/assets/8d6f8dbd-dc0e-4a51-baaf-72b248f644b3" />


- Soporte:


<img width="900" alt="image" src="https://github.com/user-attachments/assets/6b69010d-b255-4d6c-9f47-eb413af8d2db" />


**Familiares**

- Incio:

  
<img width="900" alt="image" src="https://github.com/user-attachments/assets/4ea3b1e8-ebe7-4881-a3d5-1bf56ce99618" />


- Descripción:

  
<img width="900" alt="image" src="https://github.com/user-attachments/assets/ab0f85bc-daef-49ef-8eec-5dd8fe2c7070" />


- Objetivos:

  
<img width="900" alt="image" src="https://github.com/user-attachments/assets/25d63c22-78e4-4871-bdce-049597b8d926" />


- Planes:

  
<img width="900" alt="image" src="https://github.com/user-attachments/assets/d638748d-3218-4181-b816-ed2fbb325cc0" />


- Soporte:

  
<img width="900" alt="image" src="https://github.com/user-attachments/assets/9c4fdabf-0a1f-4904-be7d-788d2092f61c" />




#### 5.2.1.6. Services Documentation Evidence for Sprint Review

Durante el Sprint 1 no se implementaron RESTful Web Services debido a que el alcance estuvo enfocado en la construcción inicial de la Landing Page.

La documentación de endpoints, Swagger/OpenAPI y pruebas mediante Postman será desarrollada en los siguientes Sprints cuando se implemente la capa backend de VitaLink.

#### 5.2.1.7. Software Deployment Evidence for Sprint Review


Durante el Sprint 1 se realizó el despliegue de la primera versión funcional de la Landing Page de VitaLink. El objetivo de esta actividad fue publicar el sitio web en un entorno accesible públicamente, permitiendo validar su funcionamiento fuera del entorno local de desarrollo.

Para el despliegue se utilizó **GitHub Pages**, aprovechando su integración directa con el repositorio de la Landing Page y su capacidad para publicar sitios web estáticos desarrollados con HTML, CSS y JavaScript.


<img width="900" alt="image" src="https://github.com/user-attachments/assets/8fc24562-7d9f-4a72-b364-92015514e330" />


#### Proceso de despliegue

Los pasos de configuración se describen a continuación como guía de reproducción. La evidencia del despliegue realizado es el workflow exitoso E-08 y la URL pública observada E-04; no se infiere que cada paso de esta guía tenga una captura histórica propia.

1. Crear el repositorio correspondiente a la Landing Page de VitaLink dentro de GitHub.

2. Subir e integrar en la rama principal los archivos HTML, CSS, JavaScript y recursos estáticos necesarios para el funcionamiento del sitio.

3. Ingresar a la configuración del repositorio mediante la opción `Settings`.

4. Acceder a la sección `Pages` dentro de la configuración del repositorio.

5. Configurar el origen del despliegue seleccionando la rama `main` y la carpeta raíz `/`.

6. Guardar la configuración para iniciar el proceso de publicación mediante GitHub Pages.

7. Esperar a que GitHub complete el proceso de despliegue y genere la URL pública correspondiente.

8. Acceder a la URL generada y verificar que la Landing Page se visualice correctamente y que sus principales secciones funcionen según lo esperado.

#### 5.2.1.8. Team Collaboration Insights during Sprint

Durante el Sprint 1, el equipo trabajó de manera colaborativa utilizando GitHub como plataforma principal para el control de versiones y seguimiento de los aportes realizados durante el desarrollo de la Landing Page de VitaLink.

Cada integrante participó en las actividades asignadas mediante ramas independientes creadas a partir de la rama `develop`. Las funcionalidades desarrolladas fueron posteriormente integradas mediante Pull Requests, permitiendo revisar los cambios antes de incorporarlos al proyecto.

Los integrantes y sus respectivos usuarios de GitHub son:

| Team Member | GitHub Username |
|---|---|
| Fernando Contreras | FernSkibidi69 |
| Pablo Martinez | Delzekl |
| Yazid Said | BL4Z3K4D |
| Kirk Quiliano | Kirkcito |
| Deiby Vargas | poluxbinPe |

Durante el Sprint se utilizó una estrategia basada en GitFlow, manteniendo la rama `develop` como rama de integración y utilizando ramas `feature/*` para las funcionalidades desarrolladas.

Asimismo, los commits realizados durante la implementación siguieron la convención Conventional Commits, facilitando la identificación de cambios relacionados con nuevas funcionalidades, correcciones, documentación y estilos.

La colaboración del equipo será evidenciada mediante las estadísticas y registros disponibles en GitHub.

Link de commits del repositorio del reporte: [https://github.com/CodeBrokers-VitaLink/upc-pre-202620-1asi0729-7737-CodeBrokers-Report/compare/main...develop]

Link de commits del repositorio del landing page: [https://github.com/CodeBrokers-VitaLink/upc-pre-202620-1asi0729-7737-CodeBrokers-Landin_Page/compare/main...develop]

Durante el desarrollo del proyecto VitaLink, todos los integrantes del equipo participaron activamente en las diferentes actividades correspondientes al ciclo de desarrollo del producto.

Las contribuciones del equipo no se limitan únicamente a los commits visibles en la sección de Contributors de GitHub, ya que algunos aportes fueron realizados mediante la organización de tareas, revisión de documentación, planificación de Sprints, diseño UX/UI, validación de entregables y coordinación del desarrollo.

Report:


<img width="900" alt="image" src="https://github.com/user-attachments/assets/75cb0925-8cb5-488c-a456-901cf1dc6c8d" />
<img width="900" alt="image" src="https://github.com/user-attachments/assets/f94d5864-7c0a-4518-8b8d-7615390a0d57" />
<img width="900" alt="image" src="https://github.com/user-attachments/assets/a33fec15-a3ff-4f29-b64d-6818616b9c82" />
<img width="900" alt="image" src="https://github.com/user-attachments/assets/341dabe8-b61b-4c9d-9592-6e00fb219b7e" />
<img width="900" alt="image" src="https://github.com/user-attachments/assets/1388511b-9263-4cbf-8b1b-c824ab8cec1c" />
<img width="900" alt="image" src="https://github.com/user-attachments/assets/767ba4fc-aee1-492a-af96-2c59a7461318" />
<img width="900" alt="image" src="https://github.com/user-attachments/assets/bb16ed5d-b23b-40b9-9495-169ee67222b9" />
<img width="900" alt="image" src="https://github.com/user-attachments/assets/c9ee272f-96e9-4e85-82d4-9ddb3439d4f6" />
<img width="900" alt="image" src="https://github.com/user-attachments/assets/1c31c7f1-b182-44f6-9bb0-a36f0c1cba17" />


Landing page:


<img width="900" alt="image" src="https://github.com/user-attachments/assets/a7ab456d-0942-413f-8609-8f3e66d9f866" />
<img width="900" alt="image" src="https://github.com/user-attachments/assets/fed9acec-0dc0-43c3-b1d1-974aa4301178" />

### 5.2.2. Sprint 2

Durante el Sprint 2, el equipo se enfocará en desarrollar y desplegar la primera versión de la **Frontend Web Application de VitaLink utilizando Angular**.

El alcance estará orientado a implementar las primeras interfaces destinadas a profesionales de salud y familiares/adultos mayores, permitiendo visualizar alertas, identificar su nivel de urgencia, acceder al detalle de pacientes y realizar acciones básicas ante una alerta.

Asimismo, durante este Sprint se realizará una actualización de la Landing Page desarrollada previamente.

#### 5.2.2.1. Sprint Planning 2

Durante el Sprint Planning 2, el equipo definió como objetivo principal desarrollar la primera versión funcional y desplegable de la Frontend Web Application de VitaLink.

Para ello, se seleccionaron User Stories correspondientes a las épicas **EP-02 Monitoreo Clínico y Gestión de Alertas** y **EP-03 Acompañamiento Familiar y Autocuidado**.

| Sprint # | Sprint 2 |
|---|---|
| **Sprint Planning Background** | |
| **Date** | 2026-09-15 |
| **Time** | 7:00 PM |
| **Location** | Reunión virtual mediante Discord |
| **Prepared By** | Yazid Said |
| **Attendees (to planning meeting)** | Fernando Contreras, Pablo Martinez, Yazid Said, Kirk Quiliano, Deiby Vargas |
| **Sprint 1 Review Summary** | Durante el Sprint 1 se desarrolló la primera versión de la Landing Page de VitaLink, incluyendo las secciones asociadas a la épica EP-01 Captación y Confianza. Asimismo, se realizó su despliegue inicial y se estableció el flujo de trabajo mediante GitHub y Git Flow. |
| **Sprint 1 Retrospective Summary** | El equipo identificó la necesidad de mantener una distribución clara de tareas, realizar integraciones progresivas mediante Pull Requests y verificar continuamente la consistencia entre los diseños UX/UI y la implementación. Para el Sprint 2 se priorizará una mejor coordinación entre diseño, desarrollo e integración. |
| **Sprint Goal & User Stories** | |
| **Sprint 2 Goal** | Nuestro enfoque está en desarrollar y publicar la primera versión funcional de la Frontend Web Application de VitaLink. Creemos que esto permitirá que profesionales de salud, familiares y adultos mayores puedan visualizar información relevante sobre el estado de salud y las alertas de una manera simple y comprensible. Esto se confirmará cuando las principales interfaces correspondientes a las User Stories seleccionadas puedan ejecutarse correctamente desde la aplicación web desplegada. |
| **Sprint 2 Velocity** | 19 Story Points |
| **Sum of Story Points** | 19 Story Points |

**Reconciliación del alcance seleccionado.** Las siete historias conservan las estimaciones del Product Backlog; no se cambian historias ni tareas. El valor 18 del borrador no coincide con esa selección y se corrige a 19 SP. La velocidad indicada aquí es la referencia planificada para este alcance, no una velocidad observada ni puntos aceptados.

| Historia seleccionada | Story Points en Product Backlog |
|---|---:|
| US-11 | 3 |
| US-12 | 2 |
| US-13 | 2 |
| US-18 | 2 |
| US-19 | 3 |
| US-20 | 2 |
| US-25 | 5 |
| **Total del Sprint 2** | **19** |

Fuente: [3.3. Product Backlog](../30-chapter-three/33-product-backlog.md). Las horas de las siete tareas del Sprint 2 suman 29 y se mantienen independientes de los Story Points.


#### 5.2.2.2. Aspect Leaders and Collaborators

Durante el Sprint 2 se identificaron los principales aspectos relacionados con el desarrollo de la primera versión de la Frontend Web Application.

Cada aspecto cuenta con un **Leader (L)**, responsable de orientar su desarrollo, y **Collaborators (C)**, quienes apoyarán las actividades correspondientes.

| Team Member | GitHub Username | Medical Frontend | Family Frontend | UX/UI & Accessibility | Sprint Documentation | Integration & Deployment |
|---|---|---|---|---|---|---|
| Fernando Contreras | FernSkibidi69 | C | L | C |  | C |
| Pablo Martinez | Delzekl | C | C | L | C |  |
| Yazid Said | BL4Z3K4D | L | C | C | C | C |
| Kirk Quiliano | Kirkcito |  | C |  | L | C |
| Deiby Vargas | poluxbinPe | C | C | C | C | L |

**L:** Leader  
**C:** Collaborator

La distribución planteada permite relacionar los aspectos del Sprint con las tareas seleccionadas posteriormente en el Sprint Backlog.

Yazid Said liderará principalmente las interfaces dirigidas a profesionales de salud, Fernando Contreras las interfaces dirigidas a familiares y adultos mayores, Pablo Martinez la consistencia UX/UI y accesibilidad, Kirk Quiliano la documentación del Sprint y Deiby Vargas la integración y despliegue.

#### 5.2.2.3. Sprint Backlog 2

Durante el Sprint 2, el equipo se enfocará en implementar las principales interfaces de la primera versión de la Frontend Web Application de VitaLink.

Las User Stories seleccionadas permitirán desarrollar vistas iniciales para profesionales de salud, familiares y adultos mayores. Para la gestión de las actividades se utilizará **Trello**, donde cada Work-item/Task será organizado de acuerdo con su estado de avance.

**Sprint Board:** Trello

**URL del Sprint Board:** Pendiente de completar.

> Insertar aquí screenshot del Board correspondiente al Sprint 2.

| Sprint # | Story Id | Story Title | Task Id | Task Title | Task Description | Estimation (Hours) | Assigned To | Status |
|---|---|---|---|---|---|---:|---|---|
| Sprint 2 | US-11 | Resumen inicial de alertas pendientes | T11 | Implement medical alert dashboard | Desarrollar el panel principal del médico mostrando la cantidad de alertas pendientes agrupadas según su nivel de urgencia. | 5 | Yazid Said | To-do |
| Sprint 2 | US-12 | Nivel de urgencia diferenciado | T12 | Implement urgency indicators | Implementar elementos visuales que permitan distinguir rápidamente el nivel de urgencia de cada alerta sin abrir su detalle. | 3 | Pablo Martinez | To-do |
| Sprint 2 | US-13 | Acceder al detalle de un paciente | T13 | Implement patient detail view | Desarrollar la vista que permita acceder al detalle del paciente directamente desde una alerta seleccionada. | 5 | Yazid Said | To-do |
| Sprint 2 | US-18 | Estado general al abrir la app | T14 | Implement family status dashboard | Desarrollar la pantalla principal para familiares y adultos mayores mostrando un indicador simple del estado general. | 5 | Fernando Contreras | To-do |
| Sprint 2 | US-19 | Recibir una alerta comprensible | T15 | Implement family alert view | Implementar una alerta que presente de forma clara qué ocurrió, su gravedad y el estado actual de atención. | 4 | Fernando Contreras | To-do |
| Sprint 2 | US-20 | Confirmar atención con una acción simple | T16 | Implement alert confirmation | Implementar una acción sencilla que permita confirmar la atención de una alerta y reflejar visualmente su nuevo estado. | 3 | Deiby Vargas | To-do |
| Sprint 2 | US-25 | Modo de uso extremadamente simple | T17 | Simplify primary interactions | Adaptar las principales interacciones de la aplicación para que puedan completarse utilizando un máximo de dos pasos. | 4 | Pablo Martinez | To-do |

**Sprint Velocity:** 19 Story Points

**Sum of Story Points:** 19 Story Points

#### 5.2.2.4. Development Evidence for Sprint Review

Durante el Sprint 2 se realizará la implementación de la primera versión de la **Frontend Web Application de VitaLink utilizando Angular, TypeScript, HTML y CSS**.

El desarrollo se organizará mediante ramas feature creadas a partir de `develop`. Una vez finalizada cada funcionalidad, los cambios serán revisados e integrados mediante Pull Requests.

La siguiente tabla será completada utilizando los commits reales realizados durante el Sprint.

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Committed on |
|---|---|---|---|---|---|
| vitalink-frontend | feature/medical-dashboard | Pendiente | feat: add medical alerts dashboard | Implement initial alert summary dashboard for healthcare professionals. | Pendiente |
| vitalink-frontend | feature/urgency-indicators | Pendiente | feat: add urgency indicators | Add visual differentiation for alert urgency levels. | Pendiente |
| vitalink-frontend | feature/patient-detail | Pendiente | feat: add patient detail view | Implement patient information view accessible from an alert. | Pendiente |
| vitalink-frontend | feature/family-dashboard | Pendiente | feat: add family status dashboard | Implement general health status interface for relatives and older adults. | Pendiente |
| vitalink-frontend | feature/family-alerts | Pendiente | feat: add family alert interface | Add understandable alert information for family users. | Pendiente |
| vitalink-frontend | feature/alert-confirmation | Pendiente | feat: add alert confirmation | Implement simple alert attention confirmation interaction. | Pendiente |
| vitalink-frontend | feature/accessibility | Pendiente | feat: simplify primary interactions | Improve navigation and reduce the number of steps in primary actions. | Pendiente |

> Los Commit Id, fechas y datos definitivos serán reemplazados con información real obtenida desde GitHub.

#### 5.2.2.5. Execution Evidence for Sprint Review

Durante el Sprint 2 se validará la ejecución de las principales interfaces desarrolladas para la primera versión de la Frontend Web Application.

Las evidencias deberán demostrar el funcionamiento de las User Stories seleccionadas y permitir comprobar que las interfaces implementadas cumplen con los objetivos definidos durante el Sprint Planning.

> Insertar capturas de las interfaces ejecutándose correctamente.

#### 5.2.2.6. Services Documentation Evidence for Sprint Review

Durante el Sprint 2 no se contempla todavía la implementación de los **RESTful Web Services de VitaLink**.

El alcance de este Sprint está enfocado principalmente en la implementación y despliegue de la primera versión de la Frontend Web Application.

Las interfaces utilizarán información simulada o datos temporales para representar los diferentes estados y escenarios necesarios para validar la experiencia de usuario.

La implementación de los RESTful Web Services mediante **Java, Spring Boot y Spring Data JPA**, junto con su documentación mediante **OpenAPI y Swagger**, será desarrollada en el siguiente Sprint.

#### 5.2.2.7. Software Deployment Evidence for Sprint Review

Durante el Sprint 2 se realizará el despliegue de una nueva versión de la Landing Page y de la primera versión de la Frontend Web Application de VitaLink.

##### Nueva versión de Landing Page

La Landing Page será actualizada considerando los ajustes o mejoras identificados después del Sprint 1.

**Repositorio:** Pendiente de completar.

**URL desplegada:** Pendiente de completar.

> Insertar captura de la nueva versión de la Landing Page publicada.

##### Primera versión de Frontend Web Application

La Frontend Web Application desarrollada con Angular será publicada para permitir el acceso público a las principales interfaces implementadas durante el Sprint.

El proceso de despliegue comprenderá:

1. Integrar las funcionalidades completadas en la rama correspondiente.
2. Generar el build de producción de la aplicación Angular.
3. Configurar el repositorio para el despliegue.
4. Publicar la aplicación mediante GitHub Pages.
5. Verificar el funcionamiento de las interfaces desde la URL pública.

**Repositorio de Frontend Web Application:** Pendiente de completar.

**URL desplegada:** Pendiente de completar.

##### Evidencias

> Insertar captura del repositorio utilizado para el despliegue.

> Insertar captura de la Frontend Web Application desplegada.

#### 5.2.2.8. Team Collaboration Insights during Sprint

Durante el Sprint 2, los integrantes colaborarán en el desarrollo de la primera versión de la Frontend Web Application utilizando GitHub como plataforma de control de versiones y colaboración.

Los integrantes y sus usuarios de GitHub son:

| Team Member | GitHub Username |
|---|---|
| Fernando Contreras | FernSkibidi69 |
| Pablo Martinez | Delzekl |
| Yazid Said | BL4Z3K4D |
| Kirk Quiliano | Kirkcito |
| Deiby Vargas | poluxbinPe |

Las funcionalidades serán implementadas mediante ramas feature y posteriormente integradas hacia `develop` mediante Pull Requests.

Las evidencias de colaboración correspondientes al Sprint 2 incluirán:

**Evidencia 1: Contributors**

> Insertar captura de GitHub Insights mostrando la participación de los integrantes.

**Evidencia 2: Commits**

> Insertar captura del historial de commits correspondientes al Sprint 2.

**Evidencia 3: Branches**

> Insertar captura de las ramas utilizadas para desarrollar las funcionalidades del Frontend Web Application.

**Evidencia 4: Pull Requests**

> Insertar captura de los Pull Requests realizados durante la integración.

**Evidencia 5: Network Graph**

> Insertar captura de GitHub Insights > Network mostrando las ramas e integraciones realizadas.

Estas evidencias permitirán identificar los aportes realizados por cada integrante y mantener trazabilidad sobre el trabajo colaborativo desarrollado durante el Sprint 2.
