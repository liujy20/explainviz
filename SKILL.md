---
name: explainviz
description: Route visualization requests to concise Mermaid, HTML-based charts, maps, geometry, or interface prototypes. Use when a visual explanation improves understanding; not for ordinary tables, production UI implementation, or publication-grade scientific figures.
---

# Explainviz

Choose the smallest useful visual representation for the user's question. Keep the explanation concise and state assumptions or limits where they matter.

Choose delivery by purpose: return inline Mermaid for static node relationships; render other static explanations in HTML and show a screenshot, retaining the source. For parameter exploration, filtering, spatial rotation, or prototypes, deliver a usable interactive file with a default-state preview.

## Routes

- For static nodes and edges, return Mermaid source. For a browser preview or screenshot, adapt [the HTML + Mermaid example](assets/examples/router-node.html).
- For changing data, maps, or time-based views, follow [data visualizations](references/visualize-data.md).
- For geometric or topological reasoning, read [geometry guidance](references/geometry-visual-explainer.md). Use [D3 for planar coordinates](assets/examples/geometry-node.html) and [Three.js for spatial curves and surfaces](assets/examples/geometry-3d-node.html); use symbolic diagrams when those suffice.
- For interactive fragments, follow [interaction guidance](references/visualize-interaction.md) and adapt [the fragment example](assets/examples/interactive-fragment.html).
- For interface previews, read [mockup guidance](references/visualize-mockups.md).
- For Mermaid source analysis, syntax repair, or design documents, use [the Mermaid design-document workflow](references/design-doc-mermaid.md).

## Browser Deliverables

Follow [HTML delivery guidance](references/visualize.md) for host fragments versus standalone browser files, visual style, and accessibility.

Use a scoped fragment only when the host supports it; otherwise deliver standalone HTML. Pin browser-importable dependencies and disclose that CDN imports need network access. Inspect the default view, key boundary states, and actual interactions before capturing the result. Avoid Python renderers, package-install steps, build steps, and user-facing local-server requirements unless needed by the task. `assets/examples/` contains source templates.
