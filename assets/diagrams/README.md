# Diagramas de VitaLink para TB2

Cada figura tiene un PNG para el informe, un SVG editable y una fuente PlantUML. Los SVG y PNG usan la misma composición. Los archivos PlantUML mantienen la notación C4-PlantUML o UML/ER y pueden producir una composición distinta.

| Archivos | Sección | Contenido |
|---|---|---|
| `c4-01-context` | 4.6.2 | Nivel 1: contexto del sistema. |
| `c4-02-container` | 4.6.3 | Nivel 2: Landing, Web Application, API y almacenamiento. |
| `c4-03` a `c4-07` | 4.6.4 | Nivel 3: componentes de Landing, SPA y API. |
| `uml-*` | 4.7.1 | Clases de IAM, Care, Providers, Enrollment y Angular. |
| `er-*` | 4.8.1 | Tablas inferidas del mapeo JPA. |

Para regenerar con PlantUML instalado, ejecutar `plantuml -tsvg assets/diagrams/*.puml` o `plantuml -tpng assets/diagrams/*.puml`. La exportación incluida se generó a partir de una composición SVG y se rasterizó con GdkPixbuf. El modelo se cotejó con el corte de repositorios del Anexo A. Las líneas discontinuas de ER marcan asociaciones lógicas, salvo que la leyenda indique otra cosa; el esquema de producción sigue pendiente de cotejo.
