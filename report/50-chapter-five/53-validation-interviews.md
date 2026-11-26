### 5.3. Validation Interviews

En esta sección se documenta el proceso de validación de **VitaLink** mediante entrevistas realizadas a usuarios representativos de los segmentos objetivo del proyecto.

El propósito de estas sesiones es evaluar la experiencia de los usuarios al interactuar con la **Landing Page** y la **Frontend Web Application**, identificando su nivel de comprensión de la propuesta de valor, facilidad de navegación, claridad de la información presentada, utilidad de las funcionalidades implementadas y posibles oportunidades de mejora.

Las entrevistas de validación se encuentran dirigidas a los dos segmentos objetivo definidos para VitaLink:

- **Segmento 1:** Adultos mayores y sus familiares que requieren acompañamiento preventivo.
- **Segmento 2:** Profesionales de salud y representantes de clínicas u hospitales.

Durante las sesiones, los participantes deberán realizar diferentes tareas utilizando los productos digitales de VitaLink mientras se observa su comportamiento y se recopilan comentarios acerca de su experiencia.

Los resultados obtenidos serán utilizados posteriormente para identificar problemas de usabilidad, arquitectura de información y accesibilidad, así como para plantear mejoras sobre la experiencia de usuario.

El proceso de validación se divide en las siguientes secciones:

- **5.3.1. Diseño de Entrevistas:** definición de objetivos, estructura, tareas, user flows y preguntas que serán utilizadas durante las sesiones.
- **5.3.2. Registro de Entrevistas:** documentación de los participantes, evidencias de las sesiones y principales observaciones obtenidas.
- **5.3.3. Evaluaciones según heurísticas:** análisis de los problemas identificados mediante criterios de usabilidad, arquitectura de información e Inclusive Design.

---

#### 5.3.1. Diseño de Entrevistas

En esta sección se presenta el diseño de las entrevistas de validación de **VitaLink**, cuyo propósito es evaluar la experiencia de los usuarios al interactuar con la Landing Page y con la Frontend Web Application desarrollada.

Las sesiones estarán dirigidas a usuarios representativos de los dos segmentos objetivo definidos para el proyecto: **adultos mayores y sus familias que requieren acompañamiento preventivo**, y **profesionales de salud y representantes de clínicas u hospitales**.

Durante las entrevistas se observará la interacción del participante con los principales flujos de VitaLink y posteriormente se recogerán sus apreciaciones acerca de la claridad de la propuesta de valor, facilidad de navegación, comprensión de las alertas, visualización de información de salud, accesibilidad y utilidad general de la solución.

Para TB2 se planifican **3 a 5 entrevistas por segmento** con la Landing Page y la Web Application de la entrega. La moderación usará cuentas y datos de prueba, una versión identificada y tareas equivalentes para comparar resultados. Se registrará si la persona completó cada tarea de forma autónoma, con ayuda o si quedó bloqueada, junto con su comentario y el momento de la grabación.

##### Objetivos de las entrevistas de validación

Las entrevistas de validación tienen como principales objetivos:

1. Evaluar si los usuarios comprenden correctamente la propuesta de valor de VitaLink desde la Landing Page.
2. Comprobar si la navegación entre las principales secciones de la Landing Page y la Web Application resulta clara.
3. Evaluar si los usuarios pueden identificar rápidamente el estado general de un adulto mayor.
4. Determinar si las mediciones de salud presentadas resultan comprensibles.
5. Evaluar la claridad de las alertas y de sus niveles de urgencia.
6. Verificar si los profesionales de salud pueden identificar y priorizar casos que requieren atención.
7. Evaluar si los familiares pueden comprender qué ocurrió y el estado actual de una alerta.
8. Identificar dificultades relacionadas con usabilidad, arquitectura de información y accesibilidad.
9. Recoger sugerencias de mejora para futuras versiones de VitaLink.
10. Conocer el nivel general de satisfacción de los participantes con la solución.

##### Estructura de la sesión de validación

Cada sesión de validación estará dividida en tres etapas principales.

**Etapa 1: Datos generales del participante**

Antes de iniciar la interacción con el producto se recopilará la siguiente información:

- Nombres y apellidos.
- Edad.
- Distrito de residencia.
- Ocupación.
- Segmento objetivo al que pertenece.
- Relación con el cuidado de adultos mayores, cuando corresponda.

**Etapa 2: Interacción con VitaLink**

El participante realizará un conjunto de tareas utilizando la Landing Page y la Frontend Web Application.

Durante esta etapa se observará si puede completar cada actividad sin asistencia y se registrarán dificultades, dudas, errores de navegación y comentarios espontáneos.

**Etapa 3: Preguntas de validación**

Después de completar las tareas, se realizarán preguntas abiertas para conocer la percepción del participante sobre la solución y las funcionalidades utilizadas.

---

##### Segmento 1: Adultos mayores y sus familias que requieren acompañamiento preventivo

Para este segmento se evaluará principalmente la facilidad con la que un familiar o adulto mayor puede comprender el estado general de salud, visualizar mediciones y reconocer situaciones que requieren atención.

###### User Flow de validación

El recorrido propuesto parte de la Landing Page y de una cuenta familiar con un paciente asociado, mediciones simuladas y al menos una alerta de prueba.

1. Elegir la vista de familias y explicar qué ofrece VitaLink tras revisar «Cómo funciona».
2. Seguir el llamado a la acción hasta la pantalla de acceso. Si se evalúa el alta, abrir «Crear cuenta», elegir el perfil familiar, asociar al paciente y a su médico, revisar el consentimiento e ingresar las mediciones simuladas.
3. Iniciar sesión y localizar el estado general en el panel familiar (`/family/dashboard`).
4. Consultar las mediciones, aplicar el filtro por nivel y explicar qué muestra el resumen semanal.
5. Ubicar una alerta abierta e interpretar su tipo, gravedad y estado. Identificar el valor y la unidad si la alerta tiene una medición vinculada.
6. Revisar la red de cuidado y el perfil. Una persona mayor con cuenta de paciente puede hacer el recorrido de autocuidado en `/patient/dashboard` con sus propios datos de prueba.

Se observará si cada persona distingue entre el estado de una alerta, el resultado de una medición y una observación del médico. La confirmación familiar de alertas, el SOS multicanal y la entrega de SMS quedan fuera de estas tareas.

###### Preguntas de validación

1. ¿Qué entendió que ofrece VitaLink después de revisar la Landing Page?
2. ¿Le quedó claro para quién está dirigida la plataforma?
3. ¿La información presentada en la Landing Page le generó confianza? ¿Por qué?
4. ¿Le resultó sencillo ingresar y orientarse dentro de la aplicación?
5. Al ingresar al dashboard, ¿pudo identificar rápidamente cómo se encuentra el adulto mayor?
6. ¿Las mediciones de salud mostradas fueron fáciles de comprender?
7. ¿Pudo identificar rápidamente si existía alguna situación que requería atención?
8. ¿La información de las alertas le pareció suficientemente clara para comprender qué ocurrió?
9. ¿Le resultó sencillo diferenciar información normal de información que requiere atención?
10. ¿La navegación entre el dashboard, red familiar y perfil le resultó clara?
11. ¿Hubo alguna opción, texto o elemento que le generara confusión?
12. ¿Considera que el tamaño de los textos, botones y elementos de navegación facilita el uso de la plataforma?
13. ¿Qué fue lo que más le gustó de VitaLink?
14. ¿Qué fue lo que menos le gustó?
15. ¿Qué funcionalidad considera que debería mejorarse o añadirse?
16. En una escala del 1 al 5, ¿cómo calificaría su experiencia general utilizando VitaLink?
17. ¿Utilizaría VitaLink para mantenerse informado sobre el estado de un familiar adulto mayor?
18. ¿Recomendaría la plataforma a otras familias? ¿Por qué?

---

##### Segmento 2: Profesionales de salud y representantes de clínicas u hospitales

Para este segmento se evaluará principalmente la capacidad de la plataforma para ayudar a los profesionales de salud a identificar alertas pendientes, reconocer su nivel de urgencia y consultar información relevante de los pacientes.

###### User Flow de validación

El recorrido propuesto parte de la Landing Page y de una cuenta de médico con pacientes vinculados, mediciones y una alerta abierta de prueba.

1. Elegir la vista profesional y localizar las secciones de alertas y seguridad. Explicar qué información necesita antes de registrar datos.
2. Seguir «Unirme como proveedor» hasta el acceso. Si se evalúa el alta, abrir «Crear cuenta» y elegir médico independiente o asociado a una clínica.
3. Iniciar sesión, revisar los conteos del panel médico (`/doctor/dashboard`) y filtrar alertas por estado.
4. Abrir una alerta, localizar al paciente y revisar la medición relacionada y el historial de intervenciones.
5. Buscar al paciente en `/doctor/patients`, abrir su ficha y localizar los registros previos.
6. En el entorno de prueba, actualizar el estado de la alerta; para marcarla como atendida, ingresar una nota. Volver al historial y localizar autor, hora y observación.

Los representantes sin función clínica pueden evaluar la Landing Page y comentar la pertinencia del recorrido profesional sobre una demostración con datos simulados. Se registrará qué tareas ejecutó cada participante.

###### Preguntas de validación

1. ¿Qué entendió que ofrece VitaLink a los profesionales de salud?
2. ¿La Landing Page explica claramente los beneficios de la plataforma para médicos o instituciones?
3. ¿La información presentada le generó confianza para utilizar la solución con pacientes?
4. ¿Le resultó sencillo acceder y orientarse dentro del dashboard médico?
5. ¿Pudo identificar rápidamente las alertas que requieren atención?
6. ¿Le resultó clara la diferencia entre los diferentes niveles de urgencia?
7. ¿Considera que la información presentada permite decidir qué caso atender primero?
8. ¿Le resultó sencillo acceder desde una alerta hasta la información del paciente?
9. ¿La información mostrada en el detalle del paciente le pareció organizada y comprensible?
10. ¿Los filtros y opciones disponibles facilitan la revisión de los casos?
11. ¿Hubo algún elemento cuyo significado no resultara evidente?
12. ¿Considera que la plataforma podría reducir el tiempo necesario para revisar casos pendientes?
13. ¿Qué información adicional necesitaría antes de tomar una decisión sobre un paciente?
14. ¿Qué fue lo que más le gustó de VitaLink?
15. ¿Qué fue lo que menos le gustó?
16. ¿Qué funcionalidad considera que debería mejorarse o añadirse?
17. En una escala del 1 al 5, ¿cómo calificaría su experiencia general utilizando VitaLink?
18. ¿Consideraría utilizar una plataforma como VitaLink dentro de su trabajo?
19. ¿Recomendaría VitaLink a otros profesionales o instituciones de salud? ¿Por qué?

---

##### Criterios de observación durante las sesiones

Además de las respuestas proporcionadas por los participantes, durante la interacción se observarán los siguientes aspectos:

- Capacidad para completar las tareas sin asistencia.
- Tiempo y dificultad percibida para encontrar información.
- Comprensión de etiquetas y opciones de navegación.
- Claridad de los niveles de urgencia.
- Comprensión de mediciones y estados.
- Errores o retrocesos durante la navegación.
- Elementos que generen dudas o confusión.
- Legibilidad y accesibilidad de la interfaz.
- Consistencia entre Landing Page y Web Application.
- Comentarios espontáneos y sugerencias del participante.

Los resultados obtenidos durante estas sesiones servirán posteriormente como base para el **Registro de Entrevistas** y para la **Evaluación de User Experience según heurísticas de usabilidad, arquitectura de información e Inclusive Design**.

#### 5.3.2. Registro de Entrevistas

Se conservan cuatro registros de AV2. La ronda histórica reúne tres sesiones del segmento familiar y una del profesional. Para completar la cuota del segmento profesional hacen falta al menos dos sesiones adicionales, siempre que se confirme la reutilización de la sesión registrada. Para acreditar la versión TB2 se requiere confirmar el entorno de cada sesión y si los recorridos se ejecutaron sobre esa versión.

Las capturas, enlaces y marcas de tiempo siguientes proceden del registro histórico. Los tres registros familiares remiten al mismo enlace de OneDrive y el segmento profesional tiene un enlace separado de SharePoint. Queda pendiente comprobar el acceso institucional en Stream, cotejar las marcas con las grabaciones y preparar el video consolidado del Anexo C.

##### Segmento 1: Adultos mayores y sus familias que requieren acompañamiento preventivo

###### Entrevista 1 - Samir

**Datos del entrevistado**

- **Nombre y apellidos:** Samir Choquehuanca Miranda
- **Edad:** 22 años
- **Distrito:** Lince
- **Perfil:** Familiar cuidador
- **Segmento objetivo:** Familiares y adultos mayores
- **Fecha de entrevista:** 10/11/2026
- **Entrevistador:** Quiliano Motta, Kirk Douglas
- **Timing:** 14:45
- **Duración:** 10:00 minutos

**Evidencia**

![Entrevista de validación - Samir](assets/entrevista_alejo_evidencia.png)

**Video de la entrevista:**

[Ver entrevista 1](https://1drv.ms/v/c/9e13d0eade016b07/IQAqH7X7AYghQ47YV-ZZ7aDXAZGFm_isOtLDK3q0cBdUYrs?e=QaZCrS)

**Resumen de la entrevista**

Samir evaluó VitaLink desde la perspectiva de un familiar cuidador y percibió la plataforma como una aplicación ordenada y claramente orientada al cuidado de la salud. Consideró especialmente útil la posibilidad de mantenerse informado sobre el estado de un familiar sin necesidad de consultarlo constantemente.

Durante la exploración de la solución comprendió que VitaLink conecta a los adultos mayores con sus familiares y con el personal de salud. La organización mediante encabezados y opciones del menú le permitió orientarse sin necesidad de leer todo el contenido disponible.

Durante la interacción con la Web Application navegó con comodidad entre las distintas secciones y valoró positivamente que las pantallas no presentaran una cantidad excesiva de información. Consideró que la interfaz mantiene una presentación limpia, con títulos y colores que permiten identificar los elementos más importantes.

En el dashboard familiar pudo reconocer correctamente a **Carmen Morales**, interpretar sus mediciones junto con las unidades y fechas correspondientes e identificar cuál era el registro más reciente. Asimismo, distinguió las alertas abiertas de los casos que se encontraban en seguimiento e identificó correctamente el estado y el profesional responsable de cada caso.

El cambio de idioma tampoco le generó dificultades durante la interacción.

Como principal punto de confusión, indicó que inicialmente no tenía claro si las alertas eran generadas automáticamente. También necesitó observar con mayor detenimiento los niveles de prioridad, aunque posteriormente logró comprenderlos al relacionarlos con las alertas mostradas.

Como oportunidades de mejora, propuso incorporar un **resumen semanal sobre la variación de las mediciones** y permitir que **varios familiares autorizados puedan realizar seguimiento al mismo adulto mayor**.

Antes de adoptar la plataforma, indicó que le gustaría conocer qué tan sencillo sería enseñar su funcionamiento a una persona mayor, si VitaLink funciona correctamente en distintos dispositivos, cómo se realiza la vinculación entre familiares y pacientes y de qué manera se protege la información personal almacenada en el sistema.

---

###### Entrevista 2 - Walter

**Datos del entrevistado**

- **Nombre y apellidos:** Walter Junior Navarro
- **Edad:** 25 años
- **Distrito:** Barranco
- **Perfil:** Familiar cuidador
- **Segmento objetivo:** Familiares y adultos mayores
- **Fecha de entrevista:** 10/11/2026
- **Entrevistador:** Quiliano Motta, Kirk Douglas
- **Timing:** 00:00
- **Duración:** 14:44 minutos

**Evidencia**

![Entrevista de validación - Walter](assets/entrevista_walter_evidencia.png)

**Video de la entrevista:**

[Ver entrevista 2](https://1drv.ms/v/c/9e13d0eade016b07/IQAqH7X7AYghQ47YV-ZZ7aDXAZGFm_isOtLDK3q0cBdUYrs?e=QaZCrS)

**Resumen de la entrevista**

Walter evaluó VitaLink desde la perspectiva de un familiar cuidador y describió la plataforma como una solución moderna, sencilla y útil para personas que tienen adultos mayores bajo su cuidado.

Durante la exploración de VitaLink logró identificar correctamente los tres tipos de usuario considerados en la plataforma y comprendió el flujo de una alerta, desde que una medición supera los límites establecidos hasta que el caso es revisado y atendido por un profesional de salud.

Consideró que la navegación resulta intuitiva y valoró positivamente el tamaño de los textos, los colores utilizados para representar los niveles de prioridad y la distribución general de la información.

En el dashboard familiar identificó correctamente a la paciente **Carmen Morales**, interpretó las mediciones junto con sus respectivas unidades y fechas, reconoció cuáles eran los registros más recientes y comprendió los estados **pendiente, en revisión y atendida**. Asimismo, pudo identificar qué profesional se encontraba atendiendo cada caso.

La funcionalidad de cambio de idioma también le resultó sencilla de utilizar.

Inicialmente tuvo dudas respecto a cómo se determinaban las alertas y quién era responsable de atenderlas. Sin embargo, estas dudas fueron resueltas conforme avanzó por las diferentes secciones de la plataforma.

Como oportunidades de mejora, propuso incorporar **gráficos de evolución de las mediciones**, un **canal de comunicación directa con el profesional de salud** y una mayor cantidad de información en cada alerta, incluyendo la medición relacionada, el valor registrado, el límite establecido, la fecha y las acciones realizadas.

Antes de adoptar VitaLink indicó que necesitaría conocer con mayor detalle cómo se protege la información médica, quiénes tienen acceso a los datos, si existen notificaciones en tiempo real y si la plataforma funciona adecuadamente desde dispositivos móviles.

---

###### Entrevista 3 - Jesus

**Datos del entrevistado**

- **Nombre y apellidos:** Jesus Arrollo
- **Edad:** 26 años
- **Distrito:** Surco
- **Perfil:** Adulto mayor
- **Segmento objetivo:** Familiares y adultos mayores
- **Fecha de entrevista:** 10/11/2026
- **Entrevistador:** Quiliano Motta, Kirk Douglas
- **Timing:** 24:46
- **Duración:** 09:53 minutos

**Evidencia**

![Entrevista de validación - Jesus](assets/entrevista_jesus_evidencia.png)

**Video de la entrevista:**

[Ver entrevista 3](https://1drv.ms/v/c/9e13d0eade016b07/IQAqH7X7AYghQ47YV-ZZ7aDXAZGFm_isOtLDK3q0cBdUYrs?e=QaZCrS)

**Resumen de la entrevista**

Jesus evaluó VitaLink desde la perspectiva de un adulto mayor y percibió la plataforma como una aplicación interesante y útil para mantenerse más informado sobre su propio bienestar.

Comprendió que VitaLink permite registrar mediciones relacionadas con la presión arterial, ritmo cardíaco y glucosa, que los familiares pueden revisar el estado general del adulto mayor y que los profesionales de salud reciben alertas cuando alguno de los valores registrados supera los límites establecidos.

Para comprender el funcionamiento de la aplicación se orientó principalmente mediante los textos, títulos, botones y diferentes secciones, utilizando también los colores como apoyo visual.

Durante la navegación no presentó mayores dificultades y valoró positivamente que la información estuviera organizada y que las principales acciones pudieran realizarse sin una cantidad excesiva de pasos.

Inicialmente tuvo dudas respecto a cómo registrar una nueva medición y qué ocurría cuando un valor resultaba anormal. Sin embargo, logró comprender estos procesos después de revisar las diferentes opciones disponibles.

Pudo identificar al paciente mediante el nombre visible en el perfil, interpretar las mediciones y sus unidades, utilizar las fechas y horas para reconocer el registro más reciente e identificar correctamente las alertas abiertas y los casos en seguimiento. También comprendió los estados **pendiente, en revisión y atendida**.

Consideró que el texto de la plataforma es legible y que los colores ayudan a diferenciar las prioridades. Sin embargo, sugirió aumentar el tamaño de algunos textos importantes y acompañar determinados símbolos con explicaciones breves para facilitar su comprensión.

El cambio de idioma le pareció una funcionalidad útil, aunque indicó que utilizaría principalmente la plataforma en español.

Entre las principales oportunidades de mejora propuso incorporar instrucciones más visibles para registrar cada medición, videos o imágenes explicativas paso a paso, gráficos sobre la evolución de las mediciones, una explicación sencilla sobre el motivo por el cual se generó cada alerta, información de contacto del médico responsable y notificaciones cuando una alerta haya sido revisada.

Antes de adoptar VitaLink indicó que quisiera conocer con mayor claridad cómo se protegen sus datos personales, qué personas pueden visualizar sus mediciones y si contaría con algún tipo de ayuda o soporte en caso de presentar dificultades durante el uso de la aplicación.

---

##### Segmento 2: Profesionales de salud y representantes de clínicas u hospitales

###### Entrevista 1 - Fátima

**Datos del entrevistado**

- **Nombre y apellidos:**  Fatima Flores Almonacid
- **Edad:** 21 años
- **Distrito:** Surco
- **Perfil:** Profesional de salud
- **Entrevistador:** Said Conde, Yazid
- **Timing:** [0:00]
- **Duración:** [6:35]

**Evidencia**

![Entrevista de validación - Fátima](assets/entrevista_fatima_evidencia.png)

**Video de la entrevista:**  
[Ver entrevista 1](https://upcedupe-my.sharepoint.com/:v:/g/personal/u202312348_upc_edu_pe/IQAJFavVDORkSraHA3bw9rVTAXQ_TWlbOHQPbGsZiEqWq5s?e=EpfTOw&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D)

**Resumen de la entrevista**

Fátima evaluó VitaLink desde la perspectiva de un profesional de salud y comprendió que la plataforma permite monitorear la salud de los pacientes, gestionar alertas y facilitar el seguimiento médico.

Consideró que la Landing Page comunica de forma clara los beneficios asociados al monitoreo continuo y al uso de alertas inteligentes. Asimismo, señaló que la información relacionada con seguridad, privacidad y seguimiento clínico contribuye a generar confianza en la solución.

Durante la interacción con la Web Application consideró que el dashboard médico presenta una estructura ordenada e intuitiva. Identificó rápidamente las alertas pendientes y pudo diferenciar sus niveles de urgencia mediante los indicadores de prioridad y los diferentes estados disponibles.

También consideró que la información mostrada permite establecer qué casos requieren una atención más inmediata.

Durante el flujo de navegación accedió con facilidad desde las alertas hasta la información correspondiente al paciente. La organización del detalle del paciente le resultó comprensible y valoró positivamente la disponibilidad de filtros por estado y prioridad, así como la funcionalidad de búsqueda de pacientes.

No identificó elementos especialmente difíciles de comprender y consideró que los íconos utilizados permiten reconocer adecuadamente las principales funciones del sistema.

Asimismo, destacó que concentrar la información de pacientes y alertas en un mismo espacio podría reducir el tiempo requerido para revisar los casos pendientes.

Como principal limitación, señaló que algunas alertas presentan poca información directamente desde la lista principal. Antes de tomar una decisión sobre un paciente, consideraría importante disponer de un historial más detallado de signos vitales y consultar las últimas intervenciones realizadas.

Como oportunidades de mejora propuso incorporar **gráficos de evolución de signos vitales** y un **resumen rápido de la información más importante de cada alerta**.

Fátima calificó su experiencia general con VitaLink con una puntuación de **5 de 5**. Indicó que utilizaría una solución como VitaLink para mejorar el seguimiento de sus pacientes y organizar sus actividades, y que la recomendaría a otros profesionales e instituciones debido a que facilita el monitoreo, la priorización de alertas y la optimización del tiempo de atención médica.




#### 5.3.3. Evaluaciones según heurísticas

```{=latex}
\begingroup
\color{blue}
```

La evaluación histórica de AV2 aplica criterios de **Usability, Inclusive Design e Information Architecture**. Se conserva su escala y la severidad asignada en esa ronda. Al final se contrasta cada hallazgo con el código disponible para TB2.

Los problemas identificados se obtuvieron a partir de las dificultades, dudas y sugerencias manifestadas por los participantes durante la interacción con la Landing Page y la Frontend Web Application.

##### UX Heuristics & Principles Evaluation

**Usability – Inclusive Design – Information Architecture**

| Campo | Información |
|---|---|
| **Carrera** | Ingeniería de Software |
| **Curso** | 1ASI0729 Desarrollo de Aplicaciones Open Source |
| **Sección** | NRC 7737 |
| **Docente** | Ivan Robles Fernández |
| **Auditor** | CodeBrokers |
| **Cliente(s)** | Samir, Walter, Jesus y Fátima |
| **Producto evaluado** | VitaLink |

**Landing Page de referencia en AV2:**
https://codebrokers-vitalink.github.io/upc-pre-202620-1asi0729-7737-CodeBrokers-Landin_Page/

**Frontend Web Application de referencia en AV2:**
https://vitalink-frontend.vercel.app/

---

##### Tareas a evaluar

El alcance de la evaluación incluye la revisión de la experiencia de usuario durante las siguientes tareas:

1. Explorar la Landing Page e identificar la propuesta de valor de VitaLink.
2. Identificar los tipos de usuarios y los principales beneficios de la plataforma.
3. Iniciar sesión y acceder al dashboard correspondiente según el rol.
4. Consultar el estado general de un adulto mayor.
5. Revisar las últimas mediciones de salud registradas.
6. Identificar alertas abiertas y sus niveles de prioridad.
7. Diferenciar los estados de una alerta: pendiente, en revisión y atendida.
8. Acceder al detalle de un paciente desde el perfil de profesional de salud.
9. Utilizar filtros y búsqueda para localizar pacientes y alertas.
10. Navegar entre las principales secciones de la Web Application.
11. Utilizar la opción de cambio de idioma.

No están incluidas dentro de esta versión de la evaluación las siguientes tareas:

1. Administración avanzada de usuarios y permisos.
2. Configuración de límites clínicos personalizados.
3. Gestión completa de múltiples familiares autorizados.
4. Comunicación directa en tiempo real entre familiares y profesionales de salud.
5. Configuración avanzada de notificaciones externas.
6. Integración con dispositivos médicos reales.

---

##### Escala de severidad

Los problemas identificados serán puntuados utilizando la siguiente escala:

| Nivel | Descripción |
|---|---|
| **1** | Problema superficial: puede ser superado fácilmente por el usuario o ocurre con muy poca frecuencia. No requiere una corrección inmediata. |
| **2** | Problema menor: genera cierta dificultad o confusión, pero el usuario puede continuar utilizando la plataforma. Debe considerarse para una próxima versión. |
| **3** | Problema mayor: dificulta considerablemente el uso de la plataforma o afecta información relevante para completar una tarea. Debe asignarse una prioridad alta. |
| **4** | Problema muy grave: impide al usuario continuar con una tarea o utilizar correctamente la herramienta. Debe ser corregido antes de una nueva versión. |

---

##### Tabla resumen

| # | Problema | Severidad | Heurística / Principio violado |
|---|---|---:|---|
| 1 | No resulta inmediatamente claro cómo y por qué se genera una alerta. | 2 | Usability: Visibility of System Status |
| 2 | Algunas alertas presentan poca información desde la lista principal. | 3 | Information Architecture: Is it Useful? |
| 3 | Las mediciones no cuentan con una representación gráfica clara de su evolución. | 2 | Usability: Recognition Rather Than Recall |
| 4 | Algunos textos, símbolos e indicadores pueden requerir mayor apoyo visual para adultos mayores. | 2 | Inclusive Design: Provide Comparable Experience |
| 5 | La información sobre privacidad, acceso a datos y autorización de familiares no resulta suficientemente visible. | 2 | Information Architecture: Is it Credible? |

---

##### Descripción de problemas

###### Problema #1: No resulta inmediatamente claro cómo y por qué se genera una alerta

**Severidad:** 2

**Heurística violada:**  
Usability – Visibility of System Status

**Problema:**

Durante las entrevistas, Samir manifestó inicialmente dudas respecto a si las alertas eran generadas automáticamente. Walter también necesitó recorrer diferentes secciones para comprender cómo se determinaban las alertas y quién debía atenderlas.

Desde la perspectiva de adulto mayor, Jesus indicó que inicialmente no comprendía qué ocurría cuando una medición presentaba un resultado anormal y posteriormente sugirió incluir una explicación sencilla sobre el motivo por el cual se genera cada alerta.

Aunque los participantes consiguieron comprender el funcionamiento después de explorar la plataforma, la relación entre una medición fuera de los límites establecidos y la generación de una alerta no siempre resulta evidente desde el primer momento.

**Recomendación:**

Incorporar dentro del detalle de cada alerta una explicación breve y visible que indique:

- medición que originó la alerta;
- valor registrado;
- rango o límite esperado;
- fecha y hora;
- nivel de prioridad;
- estado actual;
- motivo por el cual el sistema generó la alerta.

Esto permitiría que familiares, adultos mayores y profesionales comprendan inmediatamente el origen de cada alerta sin necesidad de explorar otras secciones.

**Captura:**

> Insertar captura de una alerta actual donde se evidencie la información disponible.

---

###### Problema #2: Algunas alertas presentan poca información desde la lista principal

**Severidad:** 3

**Heurística violada:**  
Information Architecture – Is it Useful?

**Problema:**

Durante la validación con el segmento profesional de salud, Fátima indicó que algunas alertas contienen poca información directamente desde la lista principal.

Aunque pudo identificar correctamente los niveles de prioridad y determinar qué casos requerían atención primero, consideró necesario disponer de mayor información antes de tomar una decisión respecto a un paciente.

Asimismo, Walter propuso que cada alerta muestre información adicional como la medición relacionada, valor registrado, límite establecido, fecha y acciones realizadas.

La falta de información resumida obliga al usuario a ingresar al detalle del caso para obtener elementos que podrían resultar importantes durante la priorización inicial.

**Recomendación:**

Agregar un resumen compacto en cada alerta mostrando como mínimo:

- nombre del paciente;
- tipo de medición;
- valor registrado;
- nivel de prioridad;
- fecha y hora;
- estado de atención;
- profesional responsable, cuando corresponda.

También se recomienda incorporar una vista rápida o resumen expandible que permita visualizar los datos esenciales sin abandonar la lista principal.

**Captura:**

> Insertar captura de la lista actual de alertas.

---

###### Problema #3: Las mediciones no cuentan con una representación gráfica clara de su evolución

**Severidad:** 2

**Heurística violada:**  
Usability – Recognition Rather Than Recall

**Problema:**

La necesidad de visualizar la evolución de las mediciones apareció repetidamente durante las entrevistas.

Samir propuso incorporar un resumen semanal de la variación de las mediciones. Walter solicitó gráficos que permitan observar la evolución de los valores registrados y Jesus realizó una sugerencia similar.

Fátima, desde la perspectiva profesional, también consideró importante disponer de gráficos de evolución de signos vitales y de un historial más detallado.

Actualmente, los usuarios pueden consultar mediciones individuales junto con sus fechas y valores. Sin embargo, comparar manualmente varios registros incrementa el esfuerzo necesario para reconocer tendencias o cambios importantes.

**Recomendación:**

Incorporar gráficos simples de evolución para las principales mediciones, como:

- ritmo cardíaco;
- saturación de oxígeno;
- presión arterial;
- glucosa.

Los gráficos podrían permitir visualizar períodos diarios, semanales o mensuales y utilizar indicadores visuales para señalar valores fuera de los rangos establecidos.

**Captura:**

> Insertar captura de la sección actual de mediciones.

---

###### Problema #4: Algunos textos, símbolos e indicadores pueden requerir mayor apoyo visual para adultos mayores

**Severidad:** 2

**Heurística violada:**  
Inclusive Design – Provide Comparable Experience

**Problema:**

Jesus evaluó VitaLink desde la perspectiva de un adulto mayor y consideró que, en términos generales, los textos resultaban legibles y los colores ayudaban a diferenciar los niveles de prioridad.

Sin embargo, señaló que algunos textos importantes podrían mostrarse con un tamaño mayor y recomendó acompañar determinados símbolos con explicaciones breves.

También indicó que instrucciones más visibles, imágenes o indicaciones paso a paso facilitarían el proceso de registrar una medición.

Aunque estas dificultades no impidieron completar las tareas, podrían afectar en mayor medida a usuarios con menor experiencia tecnológica o dificultades visuales.

**Recomendación:**

Mejorar la accesibilidad de la interfaz mediante:

- aumento del tamaño de textos críticos;
- etiquetas textuales junto a íconos importantes;
- botones con áreas de interacción suficientemente grandes;
- mayor contraste entre texto y fondo;
- instrucciones breves en procesos que puedan generar dudas;
- apoyo mediante imágenes o indicaciones paso a paso para acciones importantes.

**Captura:**

> Insertar captura de una sección con íconos o textos dirigidos al adulto mayor.

---

###### Problema #5: La información sobre privacidad, acceso a datos y autorización de familiares no resulta suficientemente visible

**Severidad:** 2

**Heurística violada:**  
Information Architecture – Is it Credible?

**Problema:**

La privacidad y el control de acceso aparecieron como preocupaciones recurrentes durante las sesiones de validación.

Samir manifestó que antes de adoptar VitaLink quisiera conocer cómo se protegen los datos personales y cómo se vinculan los familiares con el paciente.

Walter indicó que necesitaría conocer quién tiene acceso a la información médica y cómo se protege.

Jesus también señaló que quisiera saber qué personas pueden visualizar sus mediciones y cómo se protege su información.

Aunque los participantes valoraron positivamente la propuesta de seguridad presentada en VitaLink, esta información podría mostrarse con mayor claridad dentro de la propia experiencia de la Web Application.

**Recomendación:**

Incorporar una sección accesible desde el perfil donde el usuario pueda consultar claramente:

- familiares autorizados;
- profesionales con acceso al paciente;
- permisos asociados a cada usuario;
- información general sobre protección de datos;
- mecanismos para agregar o retirar accesos;
- información sobre privacidad y tratamiento de datos.

También se recomienda mostrar mensajes de confianza y privacidad en los puntos donde el usuario comparte o consulta información médica sensible.

**Captura:**

> Insertar captura de la sección de perfil o configuración relacionada con privacidad.

---

##### Resultados generales de la evaluación

La evaluación realizada permitió identificar que la experiencia general de VitaLink fue favorable para los participantes. Los usuarios lograron navegar por las principales secciones, comprender la finalidad de la plataforma, identificar mediciones y reconocer los diferentes estados de las alertas.

En el segmento familiar, los participantes valoraron especialmente la posibilidad de consultar el estado de un adulto mayor desde una interfaz centralizada, así como la organización y claridad visual de la información.

En el registro del segmento profesional se valoró disponer de pacientes y alertas en un mismo lugar para priorizar casos y consultar información clínica. Quedó pendiente medir el tiempo empleado en esas tareas.

Las principales oportunidades de mejora identificadas se concentran en proporcionar mayor detalle sobre las alertas, incorporar visualizaciones de evolución de las mediciones, reforzar algunos elementos de accesibilidad y comunicar de forma más visible los mecanismos de privacidad y control de acceso.

No se identificaron problemas de severidad **4**, debido a que ninguno de los participantes quedó impedido de continuar utilizando la plataforma. El problema de mayor prioridad corresponde a la cantidad de información disponible en las alertas, clasificado con severidad **3**, debido a su importancia para la toma de decisiones y priorización de pacientes.

Los resultados obtenidos servirán como referencia para futuras iteraciones de VitaLink, permitiendo mejorar la experiencia de familiares, adultos mayores y profesionales de salud.

##### Seguimiento técnico de hallazgos para TB2

El seguimiento se realizó mediante inspección de las revisiones de código citadas en 3.3 y comprobación de acceso a las páginas públicas de entrada. Se mantienen las severidades históricas hasta repetir las tareas con usuarios. Quedan por incorporar capturas autorizadas de cada problema en la versión evaluada.

| Hallazgo AV2 | Evidencia técnica y seguimiento | Recomendación para la ronda TB2 |
|---|---|---|
| 1. Origen de la alerta (2) | `alert-list` puede mostrar valor y unidad al familiar cuando existe una lectura vinculada. El detalle médico intenta localizar una lectura del mismo tipo cuando falta el vínculo. Sigue pendiente la claridad del motivo y del origen del dato. | Distinguir lectura vinculada y lectura de contexto. Pedir al participante que explique por qué aparece una alerta de prueba. |
| 2. Detalle en el listado (3) | Las filas muestran tipo, fecha, gravedad y estado. Solo el médico tiene enlace al detalle. El valor familiar depende del vínculo con la lectura. Cobertura parcial. | Validar primero el contexto y la acción disponible desde ambos paneles, con y sin lectura vinculada. |
| 3. Evolución de mediciones (2) | El panel familiar muestra un resumen semanal por nivel y un filtro para las lecturas recientes. Sigue pendiente comprobar la interpretación de tendencias y unidades. | Pedir que se compare una lectura reciente con el patrón de la semana y registrar las dudas. |
| 4. Apoyo visual (2) | El resumen semanal incluye etiquetas accesibles y combina símbolos con texto traducido en partes del panel. Quedan por revisar contraste, teclado, foco, tamaño y lectura de símbolos. | Verificar con personas mayores y repetir el recorrido con teclado y ampliación. |
| 5. Privacidad y autorización (2) | La Landing Page tiene sección de seguridad, el alta solicita consentimiento y el backend limita datos por vínculo. El alcance de acceso debe resultar comprensible también dentro de los paneles. | Pedir a cada participante que identifique quién puede ver los datos, con qué alcance y dónde consultarlo. |

```{=latex}
\endgroup
```
