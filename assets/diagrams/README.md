# Diagramas C4 de VitaLink

Fuentes `.puml` de los diagramas de arquitectura de software del capítulo 4. Cada fuente se versiona junto a su `.png` (para el informe) y su `.svg` (para ampliar sin pérdida).

| Fuente | Sección | Contenido |
|---|---|---|
| `c4-01-context.puml` | 4.6.2 | Nivel 1. Sistema, usuarios y sistemas externos. |
| `c4-02-container.puml` | 4.6.3 | Nivel 2. Contenedores desplegados y planificados. |
| `c4-03-components-iam.puml` | 4.6.4 | Nivel 3. Componentes del contexto IAM del WebApp. |
| `c4-04-components-care.puml` | 4.6.4 | Nivel 3. Componentes del contexto Care del WebApp. |
| `c4-05-components-backend.puml` | 4.6.4 | Nivel 3. Componentes del Backend API planificado. |

## Convención de estado

El enunciado distingue lo desplegado de lo que aún es diseño. Los diagramas lo reflejan con dos etiquetas:

- **Implementado y desplegado** (azul): existe en el front-end Angular sobre la API simulada.
- **Planificado para TB2** (gris y borde discontinuo): backend Spring Boot, base de datos y servicios externos aún no desplegados.

En los diagramas de componentes, el **modelo de dominio y el servicio de dominio** se resaltan en verde porque concentran las reglas del negocio.

## Cómo regenerar

Requiere PlantUML y Graphviz (`dot` en el `PATH`), y la biblioteca C4-PlantUML, que PlantUML descarga desde su biblioteca estándar en la primera ejecución.

```powershell
# PNG para el informe y SVG para ampliaciones
foreach ($f in Get-ChildItem assets/diagrams/*.puml) {
    java -jar plantuml.jar -tpng -charset UTF-8 $f.FullName
    java -jar plantuml.jar -tsvg -charset UTF-8 $f.FullName
}
```

La proporción de cada figura está pensada para que, al ancho indicado en el informe, el texto del diagrama se mantenga legible: `c4-01`, `c4-02`, `c4-03` y `c4-05` van a `\linewidth`, y `c4-04` a `0.70\linewidth` porque es más alta que ancha.

## Criterios de modelado

- Nivel 1: el sistema se representa como **un solo recuadro**; no se descompone en contenedores.
- Nivel 2: los contextos delimitados `care` e `iam` viven dentro del contenedor WebApp, no como contenedores aparte.
- Nivel 3: un diagrama por contexto delimitado, porque los ocho componentes de `care` en una sola figura resultaban ilegibles.
- Las descripciones de los elementos se mantienen cortas: la explicación extensa vive en la prosa del capítulo 4.

Referencia de notación: [C4 model](https://c4model.com/) y [C4-PlantUML](https://github.com/plantuml-stdlib/C4-PlantUML).
