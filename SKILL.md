---
name: explainviz
description: Route visualization requests to concise Mermaid, HTML-based charts, maps, geometry, or interface prototypes. Use when a visual explanation improves understanding; not for ordinary tables, production UI implementation, or publication-grade scientific figures.
---

# Explainviz

Choose the smallest useful visual representation for the user's question. Keep the explanation concise and state assumptions or limits where they matter.

## Routes

- For static nodes and edges, return Mermaid source. For a browser preview or screenshot, adapt [the HTML + Mermaid example](assets/examples/router-node.html).
- For changing data, maps, or time-based views, follow [data visualizations](references/visualize-data.md).
- For geometric or topological reasoning, use [the HTML + D3 geometry example](assets/examples/geometry-node.html) and [geometry guidance](references/geometry-visual-explainer.md).
- For interactive fragments, follow [interaction guidance](references/visualize-interaction.md) and adapt [the fragment example](assets/examples/interactive-fragment.html).
- For interface previews, read [mockup guidance](references/visualize-mockups.md).
- For Mermaid source analysis, syntax repair, or design documents, use [the Mermaid design-document workflow](references/design-doc-mermaid.md).

## Browser Deliverables

Follow [HTML delivery guidance](references/visualize.md) for host fragments versus standalone browser files, visual style, and accessibility.

Use standalone HTML with pinned browser-importable npm packages for layouts, charts, diagrams, and geometry operations. Keep the HTML as the editable source and use browser tooling to inspect and capture the rendered result. Avoid Python renderers, package-install steps, build steps, and local-server requirements unless the user explicitly needs them. `assets/examples/` contains source templates.
