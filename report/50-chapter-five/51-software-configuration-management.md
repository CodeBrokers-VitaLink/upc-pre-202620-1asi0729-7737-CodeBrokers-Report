## 5.1. Software Configuration Management

### 5.1.1. Software Development Environment Configuration

Para el desarrollo de VitaLink se utilizarán diferentes herramientas de software que permitirán gestionar las actividades correspondientes al ciclo de vida del producto, incluyendo la gestión del proyecto, análisis de requisitos, diseño UX/UI, desarrollo de software, documentación, control de versiones y despliegue.

---

#### Project Management

Para la gestión del proyecto y organización del Product Backlog se utilizará **Trello** como herramienta de planificación y seguimiento. Esta permitirá organizar las actividades correspondientes a cada Sprint, distribuir responsabilidades entre los integrantes y visualizar el avance de las tareas del proyecto.

Asimismo, se utilizará **GitHub Issues** para registrar incidencias y actividades relacionadas directamente con los repositorios, permitiendo mantener trazabilidad sobre los cambios y tareas técnicas realizadas durante el desarrollo.

**Enlaces:**

- [Trello](https://trello.com/)
- [GitHub Issues](https://docs.github.com/en/issues)

---

#### Requirements Management

Para la gestión y análisis de requisitos se utilizarán **UXPressia** y **Miro** como herramientas de apoyo para la elaboración de diferentes artefactos relacionados con el entendimiento de los usuarios y la definición del producto.

**UXPressia** será utilizada para la elaboración de User Personas, Empathy Maps, User Journey Maps e Impact Maps, permitiendo representar las necesidades, comportamientos y objetivos de los usuarios de VitaLink.

**Miro** será utilizado como espacio de trabajo colaborativo para organizar ideas, realizar análisis visuales y desarrollar diferentes actividades relacionadas con el descubrimiento, definición y planificación del producto.

Los criterios de aceptación correspondientes a las User Stories y Technical Stories serán redactados utilizando **Gherkin**, permitiendo definir escenarios mediante la estructura Given-When-Then.

La documentación de requisitos será almacenada dentro del repositorio del Project Report utilizando archivos Markdown gestionados mediante GitHub.

**Enlaces:**

- [UXPressia](https://uxpressia.com/)
- [Miro](https://miro.com/)
- [Gherkin Documentation](https://cucumber.io/docs/gherkin/)

---

#### Product UX/UI Design

Para el diseño de la experiencia e interfaz de usuario de VitaLink se utilizará **Figma** como herramienta principal para la elaboración de Wireframes, Mock-ups y Prototypes.

Asimismo, **Miro** será utilizado como herramienta colaborativa para organizar flujos e ideas relacionadas con la experiencia del usuario.

Para la elaboración de diagramas complementarios se utilizará **Lucidchart**.

La Frontend Web Application seguirá los principios de Material Design y utilizará **Angular Material** como biblioteca de componentes para mantener consistencia visual entre las diferentes interfaces del producto.

**Enlaces:**

- [Figma](https://www.figma.com/)
- [Miro](https://miro.com/)
- [Lucidchart](https://www.lucidchart.com/)
- [Angular Material](https://material.angular.io/)
- [Material Design](https://m3.material.io/)


#### Software Development

La solución VitaLink estará compuesta por una Landing Page, una Frontend Web Application y RESTful Web Services.

La Landing Page será desarrollada utilizando HTML5, CSS3 y JavaScript, permitiendo construir una interfaz web responsive orientada a comunicar la propuesta de valor de VitaLink.

La Frontend Web Application será desarrollada utilizando Angular Framework junto con TypeScript, además de HTML5 y CSS3 para la estructura y presentación de las interfaces.

Los RESTful Web Services serán desarrollados utilizando Java, Spring Boot Framework y Spring Data JPA, permitiendo implementar la lógica de negocio y gestionar la persistencia de información de VitaLink.

Como entornos de desarrollo se utilizarán Visual Studio Code para el desarrollo de componentes frontend, Landing Page y documentación, e IntelliJ IDEA para el desarrollo de los RESTful Web Services.

Para la gestión de dependencias de la Frontend Web Application se utilizarán Node.js y NPM.

Enlaces:

- https://angular.dev/
- https://www.typescriptlang.org/
- https://www.java.com/
- https://spring.io/projects/spring-boot
- https://spring.io/projects/spring-data-jpa
- https://code.visualstudio.com/
- https://www.jetbrains.com/idea/
- https://nodejs.org/
- https://www.npmjs.com/


#### Software Architecture and Database Design

Para la documentación de la arquitectura del software se utilizará Structurizr, permitiendo elaborar los diagramas correspondientes al C4 Model y representar la estructura de los diferentes componentes que conforman VitaLink.

Para la elaboración de diagramas UML y otros modelos visuales se utilizará Lucidchart, permitiendo representar componentes, relaciones y procesos del sistema.

Para el diseño y modelado de la base de datos se utilizará MySQL Workbench, permitiendo representar tablas, atributos, claves primarias, claves foráneas, restricciones y relaciones correspondientes al modelo de datos de VitaLink.

Enlaces:

- https://structurizr.com/
- https://www.lucidchart.com/
- https://www.mysql.com/products/workbench/


#### Software Documentation

La documentación general del proyecto será elaborada mediante archivos Markdown almacenados dentro del repositorio público del Project Report en GitHub.

Para la documentación de los RESTful Web Services se utilizará OpenAPI Specification mediante Swagger, permitiendo documentar los endpoints disponibles, métodos HTTP, parámetros, requests y responses correspondientes a los servicios implementados.

Repositorios actuales del proyecto:

- Project Report Repository:
  https://github.com/CodeBrokers-VitaLink/upc-pre-202620-1asi0729-7737-CodeBrokers-Report

- Landing Page Repository:
  https://github.com/CodeBrokers-VitaLink/upc-pre-202620-1asi0729-7737-CodeBrokers-Landin_Page

Enlaces:

- https://www.markdownguide.org/
- https://swagger.io/specification/
- https://swagger.io/

#### Software Version Control

Para el control de versiones y trabajo colaborativo se utilizarán **Git** y **GitHub**.

Git será utilizado como sistema distribuido de control de versiones, mientras que GitHub permitirá almacenar y administrar los diferentes repositorios del proyecto.

El equipo utilizará **GitFlow Workflow** para organizar las ramas de desarrollo, **Conventional Commits** para mantener un historial de modificaciones ordenado y **Semantic Versioning** para identificar las versiones liberadas de los productos de VitaLink.

**Enlaces:**

- [Git](https://git-scm.com/)
- [GitHub](https://github.com/)

---

## 5.1.2. Source Code Management

Para la gestión del código fuente y el seguimiento de modificaciones durante el desarrollo de VitaLink, se utilizará **Git como sistema de control de versiones** y **GitHub como plataforma colaborativa para almacenar, administrar y revisar los repositorios del proyecto**.

El equipo aplicará una estrategia basada en **Git Flow Workflow**, permitiendo organizar el desarrollo mediante el uso de ramas según el propósito de cada modificación realizada. Esta metodología permite mantener una rama principal con una versión estable del proyecto, mientras que las ramas de desarrollo permiten implementar nuevas funcionalidades y realizar pruebas antes de integrar los cambios al producto final.

La estructura de ramas utilizada para el desarrollo de la Landing Page de VitaLink es la siguiente:

- **main:** Rama principal que contiene la versión estable del proyecto y representa el estado preparado para despliegue.

- **develop:** Rama utilizada para integrar, validar y probar los cambios desarrollados antes de incorporarlos a la versión estable.

- **feat/family-and-clinical-sections:** Rama creada para desarrollar las secciones relacionadas con familiares y contenido clínico de la Landing Page.

- **feat/pricing-tiers-and-testimonials:** Rama creada para implementar las secciones relacionadas con planes de precios y testimonios de usuarios.

El uso de ramas independientes permite que los integrantes del equipo puedan trabajar de manera paralela sobre funcionalidades específicas sin afectar directamente la versión estable del proyecto. Una vez finalizada y validada una funcionalidad, los cambios son integrados mediante procesos de **merge** hacia la rama correspondiente.

Además, GitHub permite mantener la trazabilidad del desarrollo mediante el historial de commits, facilitando la identificación de los cambios realizados durante la implementación del proyecto. Para la descripción de modificaciones se utilizaron mensajes de commit siguiendo una estructura basada en **Conventional Commits**, permitiendo reconocer fácilmente el propósito de cada actualización.

Los principales tipos de commits utilizados fueron:

- **feat:** Utilizado para la incorporación de nuevas funcionalidades o componentes dentro del proyecto.


Enlace de la Landing Page desplegada mediante GitHub Pages: [https://codebrokers-vitalink.github.io/upc-pre-202620-1asi0729-7737-CodeBrokers-Landin_Page/]

<img width="900" alt="image" src="https://github.com/user-attachments/assets/87b3ec15-9caa-4c99-a88b-d61961d2e89c" />

Repositorio GitHub de la Landing Page: [https://github.com/CodeBrokers-VitaLink/upc-pre-202620-1asi0729-7737-CodeBrokers-Landin_Page]

<img width="900" alt="image" src="https://github.com/user-attachments/assets/58229ef4-7fb6-4070-b245-ce89d18eedf0" />

Repositorio GitHub de los archivos feature

<img width="900" alt="image" src="https://github.com/user-attachments/assets/d1c5bd44-d8aa-45b5-9120-ea35d56b9945" />

<img width="900" alt="image" src="https://github.com/user-attachments/assets/db69ab32-a093-4110-88ee-683fa27a2888" />


---

### 5.1.3. Source Code Style Guide & Conventions

Para mantener uniformidad, legibilidad y facilidad de mantenimiento en el código fuente de VitaLink, se establecieron convenciones de desarrollo para los diferentes lenguajes y tecnologías utilizados durante la implementación del proyecto.

La nomenclatura utilizada en el código será escrita en **inglés**, independientemente del lenguaje de programación empleado. Asimismo, se utilizarán nombres descriptivos que permitan identificar claramente la responsabilidad de variables, funciones, métodos, clases y componentes.

Estas convenciones tienen como objetivo asegurar una estructura organizada del código, facilitar la colaboración entre los integrantes del equipo y permitir un mantenimiento eficiente durante las diferentes etapas del desarrollo.

#### HTML

Para el desarrollo de interfaces web utilizando HTML se seguirán las siguientes convenciones:

- Se utilizarán nombres descriptivos en inglés para clases, identificadores y elementos personalizados.
- Se emplearán etiquetas semánticas de HTML5 para mantener una estructura clara y organizada del contenido.
- Se mantendrá una correcta jerarquía de encabezados utilizando etiquetas como `<h1>`, `<h2>` y `<h3>`.
- Se evitará el uso de nombres genéricos que no permitan identificar la finalidad del elemento.

Ejemplo:

```html
<section class="pricing-section">
```

En lugar de:

```html
<section class="section1">
```

Además, la estructura del documento HTML mantendrá una organización adecuada separando correctamente las diferentes secciones de la interfaz.

#### CSS

Para la definición de estilos mediante CSS se aplicarán las siguientes convenciones:

- Se utilizarán nombres descriptivos en inglés para clases y selectores.
- Se mantendrá una organización consistente de estilos según componentes o secciones de la aplicación.
- Se evitará la duplicación innecesaria de reglas CSS.
- Los nombres de clases deberán representar claramente la función del componente visual.

Ejemplo:

```css
.family-card

.pricing-container

.testimonial-section
```

En lugar de:

```css
.box1

.container2
```

Asimismo, se mantendrá una separación adecuada entre estilos generales, componentes y reglas responsive para facilitar futuras modificaciones.

#### JavaScript

Para el desarrollo con JavaScript se seguirán las siguientes convenciones:

- Se utilizarán nombres descriptivos en inglés para variables, funciones y objetos.
- Las funciones deberán representar claramente la acción que realizan.
- Se evitará la repetición de código mediante la reutilización de funciones.
- Se mantendrá una estructura organizada y modular.
- Se utilizarán comentarios únicamente cuando sean necesarios para explicar una lógica específica.

Ejemplo:

```javascript
toggleMenu()

validateForm()

calculateTotal()
```

En lugar de:

```javascript
function1()

data()
```

#### TypeScript

Para el desarrollo utilizando TypeScript se seguirán las siguientes convenciones:

- Se utilizarán nombres en inglés para interfaces, clases, tipos, variables y funciones.
- Las clases e interfaces utilizarán la nomenclatura PascalCase.
- Las variables y funciones utilizarán la nomenclatura camelCase.
- Se definirán correctamente los tipos de datos para mejorar la seguridad y comprensión del código.

Ejemplo:

```typescript
interface UserProfile {
}

class HealthRecord {
}

const userInformation = {};
```

Además, se mantendrá una estructura modular que facilite la escalabilidad y mantenimiento del sistema.

#### Java

Para el desarrollo de servicios backend utilizando Java se seguirán las convenciones recomendadas por Java Style Guide.

Las principales reglas serán:

- Utilizar PascalCase para nombres de clases.

Ejemplo:

```java
HealthService

UserController
```

- Utilizar camelCase para variables y métodos.

Ejemplo:

```java
getUserProfile()

calculateAppointment()
```

- Utilizar nombres descriptivos en inglés.
- Mantener una separación adecuada entre controladores, servicios, repositorios y entidades.
- Organizar los paquetes según la responsabilidad de cada componente.

Ejemplo:

```text
controller/

service/

repository/

entity/
```

Estas convenciones permitirán mantener una arquitectura organizada y facilitarán el mantenimiento del código backend durante las siguientes etapas del proyecto.

#### Convenciones de commits

Para mantener un historial organizado de modificaciones, los mensajes de commit seguirán una estructura basada en **Conventional Commits**.

Los principales tipos utilizados serán:

- **feat:** Utilizado para la incorporación de nuevas funcionalidades o componentes dentro del proyecto.

Ejemplo:

```text
feat: add pricing section
```

- **fix:** Utilizado para la corrección de errores o mejoras sobre funcionalidades existentes.

Ejemplo:

```text
fix: improve responsive layout
```

- **style:** Utilizado para cambios relacionados con estilos visuales y formato del código.

Ejemplo:

```text
style: update landing page styles
```

- **docs:** Utilizado para modificaciones relacionadas con documentación.

Ejemplo:

```text
docs: update project documentation
```

- **refactor:** Utilizado para reorganización o mejora del código sin modificar su comportamiento.

Ejemplo:

```text
refactor: improve component structure
```

La aplicación de estas convenciones permitirá mantener una estructura uniforme del código desarrollado, facilitando la colaboración entre integrantes, la revisión de cambios y el mantenimiento del proyecto VitaLink durante las diferentes etapas de implementación.

### 5.1.4. Software Deployment Configuration

La configuración de despliegue de VitaLink se organiza según los diferentes componentes que conforman la solución, separando la Landing Page, la aplicación web y los servicios backend. Esta distribución permite mantener una separación clara de responsabilidades entre la interfaz pública, la aplicación de usuario y los servicios internos del sistema.

Cada componente contará con su propio repositorio y configuración de despliegue, permitiendo administrar de manera independiente su ciclo de desarrollo, pruebas y publicación.

Actualmente, la primera versión desplegada corresponde a la Landing Page del proyecto, la cual fue publicada utilizando GitHub Pages debido a que está compuesta por archivos estáticos desarrollados con HTML, CSS y JavaScript.

Los componentes considerados para la configuración de despliegue son los siguientes:

| Component | Repository | Deployment platform | Main purpose |
| --- | --- | --- | --- |
| Landing Page | CodeBrokers Landing Page | GitHub Pages | Presentar la propuesta de valor de VitaLink y comunicar las principales funcionalidades del producto a los usuarios. |
| Frontend Web Application | CodeBrokers-webapp | Render | Permitir la interacción de usuarios con la plataforma mediante una aplicación web funcional. |
| RESTful Web Services | CodeBrokers-platform | Render | Proporcionar servicios backend mediante APIs REST para la comunicación con la aplicación web. |
| Report | CodeBrokers Report | GitHub | Mantener la documentación técnica, evidencias y avances del proyecto. |

La Landing Page fue desplegada mediante GitHub Pages utilizando la rama configurada para publicación del repositorio. El servicio permite generar una URL pública accesible desde cualquier navegador, facilitando la validación y demostración del avance desarrollado.

Enlace de despliegue:

https://codebrokers-vitalink.github.io/upc-pre-202620-1asi0729-7737-CodeBrokers-Landin_Page/

Para la gestión del código desplegado se mantiene una separación entre desarrollo y publicación, permitiendo realizar modificaciones mediante ramas independientes antes de integrarlas a la versión estable.

El proceso general de despliegue considera las siguientes etapas:

- Desarrollo de nuevas funcionalidades dentro de ramas específicas.
- Validación de los cambios realizados.
- Integración mediante procesos de merge hacia la rama correspondiente.
- Publicación del contenido actualizado mediante la plataforma de despliegue definida.

La configuración actual permite mantener una estructura organizada del proyecto, facilitando futuras integraciones de la Web Application y los RESTful Web Services durante las siguientes etapas de implementación de VitaLink.
