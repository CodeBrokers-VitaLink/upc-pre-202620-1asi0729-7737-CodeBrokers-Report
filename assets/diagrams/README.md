# Fuentes de diagramas de VitaLink

Los archivos `.mmd` son la fuente editable de las imágenes incluidas en 2.4, 4.6 y 4.7. `manifest.json` relaciona cada fuente con su PNG para el informe y su SVG para ampliaciones. El modelo es un diseño de dominio; los adaptadores de backend y Triage & Scheduling se indican como propuestos o futuros, sin atribuirles implementación en TB1.

Convenciones: AR = Aggregate Root; Entity = entidad interna; VO = Value Object inmutable; Enum = clasificación cerrada; DE = Domain Event. En UML, los namespaces con sufijo Aggregate delimitan el agregado, `*--` indica composición y la multiplicidad aparece junto a cada extremo. Las dependencias entre raíces usan identificadores. Los prefijos `-` y `+` indican miembros privados y operaciones públicas. Las invariantes se identifican en las notas y se describen en 4.7.

Para regenerar desde la raíz del repositorio con Node.js y PowerShell:

```powershell
$diagramManifest = Get-Content -Raw assets/diagrams/manifest.json | ConvertFrom-Json
foreach ($diagram in $diagramManifest) {
    npx --yes @mermaid-js/mermaid-cli@12.0.0 -i $diagram.source -o $diagram.png -c assets/diagrams/mermaid-config.json -b white --size 1800 -s 2
    npx --yes @mermaid-js/mermaid-cli@12.0.0 -i $diagram.source -o $diagram.svg -c assets/diagrams/mermaid-config.json -b white --size 1800
}
```

Mermaid CLI utiliza Puppeteer. Si se usa un Chrome ya instalado, proporcionar `-p` con un JSON local que especifique `executablePath`; no incluir rutas personales ni credenciales en Git.

Referencias de notación y herramienta: [Class diagrams](https://mermaid.js.org/syntax/classDiagram.html), [Flowcharts](https://mermaid.js.org/syntax/flowchart.html) y [Mermaid CLI](https://github.com/mermaid-js/mermaid-cli).
