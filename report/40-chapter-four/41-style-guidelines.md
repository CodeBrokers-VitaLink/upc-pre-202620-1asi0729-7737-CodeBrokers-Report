# Capítulo IV: Product Design

## 4.1. Style Guidelines

El diseño visual de la aplicación VitaLink sigue una estética entre lo clínico y lo confiable. Esto se relaciona con la identidad de nuestro equipo **CodeBrokers** y con el compromiso de ofrecer soluciones de software de alta calidad al sector salud, enfocadas en el monitoreo, cuidado y acompañamiento preventivo de adultos mayores.

En este capítulo se describen los estilos que se utilizan en el desarrollo de la aplicación web responsiva, siguiendo los principios de UX y UI definidos por el equipo.

### 4.1.1. General Style Guidelines

**Branding**

El logo principal representa a VitaLink, una plataforma orientada al monitoreo y seguimiento de la salud de los adultos mayores. El nombre surge de la combinación de "Vital", relacionado con los signos vitales, la salud y el bienestar, y "Link", que representa la conexión constante entre el adulto mayor, sus familiares y los profesionales o centros de salud.

La identidad visual incorpora un ícono minimalista que combina elementos relacionados con la salud, el monitoreo y la conexión. El símbolo representa una figura humana protegida dentro de una forma inspirada en un corazón, integrando además una línea de pulso o electrocardiograma. Este recurso visual comunica de manera directa el propósito de VitaLink: cuidar, monitorear y mantener conectadas a las personas involucradas en el bienestar del adulto mayor.

\begin{figure}[H]
\centering
\includegraphics[width=0.5\linewidth]{assets/logo-vitalink.png}
\caption{Logotipo de VitaLink}
\end{figure}

**Typography**

Para garantizar consistencia en toda la plataforma (Landing Page y aplicación), la única familia tipográfica empleada es **Arial**, en sus variantes Regular (400) y Bold (700).

Arial se elige por su alta legibilidad, su simplicidad geométrica y su disponibilidad nativa en ordenadores clínicos, tabletas hospitalarias y teléfonos móviles antiguos. Esto es especialmente importante en VitaLink: los adultos mayores no deben depender de la descarga de web fonts, y los familiares y médicos deben leer datos vitales sin márgenes de error. En el informe técnico, los fragmentos de código se muestran con una fuente monoespaciada; la interfaz de usuario utiliza exclusivamente Arial.

El tamaño de letra de la aplicación sigue esta distribución:

* **Títulos principales:** 2.25rem (36 px), para encabezados de dashboards y secciones importantes.
* **Subtítulos:** entre 1.5rem (24 px) y 1.75rem (28 px), para organizar la ficha del paciente.
* **Texto secundario:** entre 1.125rem (18 px) y 1.25rem (20 px), recomendado para métricas vitales que requieran gran visibilidad.
* **Cuerpo del texto:** 1rem (16 px), con interlineado de 1.5 a 1.6.
* **Información auxiliar:** 0.875rem (14 px), para marcas de tiempo, etiquetas de UI y datos complementarios.

La tipografía y los colores mantienen un contraste mínimo de 4.5:1 para texto normal, en cumplimiento de las recomendaciones de accesibilidad WCAG 2.1 AA.

**Paleta de colores y jerarquía visual**

La paleta distingue entre el color de marca y el color de acción. Los ratios de contraste se calcularon según la fórmula de luminancia relativa de WCAG.

| Rol | Color | Uso | Contraste |
|:--------------------|:---------------|:---------------------------------------------|:-----------------------------------|
| Primario de marca | Verde VitaLink `#1D9E75` | Logotipo, íconos, ilustraciones e indicadores de estabilidad (elementos no textuales) | 3.39:1 sobre blanco. Cumple el mínimo de 3:1 para componentes gráficos. No se usa como fondo de texto normal |
| Primario de acción | Verde médico `#00694C` | Botones primarios, enlaces y elementos interactivos con texto | 6.72:1 con texto blanco |
| Secundario | Verde oscuro `#0F6E56` | App Bars, Sidebars y refuerzo corporativo | 6.20:1 con texto blanco |
| Superficie | Neutro claro `#F8FAFB` | Fondo de pantallas y superficies | --- |
| Error / alerta crítica | Rojo alerta `#BA1A1A` sobre `#FFDAD6` | Métricas fuera de la línea base y acciones destructivas | 5.00:1 (sobre `#FFDAD6`) y 6.46:1 (sobre blanco) |
| Neutros | Tonos grises | Bordes de tarjetas, separadores y jerarquía de texto secundario | --- |

: Paleta de colores de VitaLink

Los estados de severidad de las alertas (Low, Medium, High) y el estado biométrico del paciente se representan siempre con color **y** con ícono o etiqueta textual, de modo que el significado nunca dependa únicamente del color (WCAG 1.4.1).

\begin{figure}[H]
\centering
\includegraphics[width=0.7\linewidth]{assets/colors.png}
\caption{Paleta de colores de VitaLink}
\end{figure}

**Spacing**

El sistema de espaciado se basa en una cuadrícula de 8 px:

* **Espaciado base de 0.5rem (8 px)** para la consistencia entre elementos pequeños.
* **Padding interno de 1.5rem a 4rem (24--64 px)** en tarjetas de pacientes y contenedores de métricas.
* **Separación de 4rem a 5rem (64--80 px)** entre secciones macro de la Landing Page.

**Tono de comunicación**

La comunicación de VitaLink busca transmitir profesionalismo clínico, confianza y empatía humana.

* **Equilibrio:** profesional pero accesible (75 % formal, 25 % humano).
* **Lenguaje:** directo, orientado a la acción y libre de jerga médica compleja cuando el rol activo es Familiar o Adulto Mayor. En el rol Profesional, el tono es técnico y preciso.

### 4.1.2. Web Style Guidelines

Esta sección describe cómo los lineamientos generales se implementan en el código web de la plataforma, unificando la Landing Page estática y la Single Page Application (SPA) en Angular. El diseño web es responsivo con enfoque *Mobile First*.

**Tipografía web unificada**

* Toda la plataforma declara `font-family: Arial, Helvetica, sans-serif;` en el `body`, de modo que no existan discrepancias tipográficas entre la Landing Page y la aplicación. No se cargan fuentes externas, lo que reduce los tiempos de carga.
* Los pesos permitidos en CSS son `400` (Regular) y `700` (Bold).

**Botones y elementos de acción**

* **Botones primarios (Call to Action):** `background-color: #00694C` (verde médico) y `color: #FFFFFF`, con `border-radius: 12px`. En la SPA, el tema de Angular Material 3 define su color primario con `#00694C`, de modo que `<button mat-flat-button>` hereda este estilo.
* **Tono de los botones:** textos cortos con verbos de acción ("Iniciar sesión", "Registrar paciente").

**Tarjetas y contenedores**

* Las tarjetas (cards) son el componente base para presentar pacientes y alertas.
* **CSS base:** `background: #FFFFFF; border: 1px solid #E1E3E4; border-radius: 16px; box-shadow: 0 4px 6px rgba(0,0,0,0.05);`.
* En la SPA se renderizan con `MatCardModule`.

**Iconografía y estado de componentes**

* Se emplea la iconografía Google Material Symbols (variante Outlined), mediante `<mat-icon>` en la SPA y clases de ícono en la Landing Page.
* Los estados de alerta cambian el contenedor completo del componente. Por ejemplo, `<div class="alert-critical">` aplica `background: #FFDAD6; color: #BA1A1A;`.

**Diseño responsivo**

* **Escritorio (>1024 px):** layout de varias columnas con CSS Grid (`grid-template-columns`) y menú lateral fijo (Sidebar).
* **Móviles (<768 px):** Grid y Flexbox pasan a `flex-direction: column`, las tarjetas ocupan el 100 % del ancho y la navegación lateral colapsa en un menú hamburguesa.