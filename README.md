# explainviz

English | [简体中文](README.zh-CN.md)

[![skills.sh](https://skills.sh/b/liujy20/explainviz)](https://skills.sh/liujy20/explainviz)

**Turn explanations into diagrams, charts, and interactive visuals.**

`explainviz` is an Agent Skill that helps your AI assistant choose a useful visual form for your question. Use it to understand a system, compare data, explore geometry, or try an interface idea. Describe what you want to understand; the skill guides the assistant in choosing and creating the visual.

## What you can do

| Task | What it can create |
| --- | --- |
| Understand processes and systems | Mermaid flowcharts, sequence diagrams, state diagrams, and entity relationships |
| Compare data and changes over time | Charts, timelines, small multiples, and interactive comparisons |
| Explore geographic patterns | Maps with data overlays, labels, and region selection |
| Understand geometry and topology | Planar diagrams, polygon operations, and rotatable 3D curves and surfaces |
| Explore how parameters affect a result | Interactive explanations with sliders, selection, and linked updates |
| Try interface ideas | Clickable HTML previews of screens, components, and design variants |

It can also explain or repair Mermaid diagrams and turn relevant source code or design notes into diagrams with supporting explanations.

## Install

Run the following command in a terminal with Node.js and npm available:

```bash
npx skills add liujy20/explainviz
```

Follow the installer prompts to select your AI assistant and installation scope. The skill uses the shared Agent Skills format; the skills CLI supports tools such as Codex, Claude Code, and Cursor. Skill discovery and preview capabilities depend on the tool you use.

## Use it

Once installed, ask your assistant to use `explainviz` and describe your question. You do not need to choose a rendering library or diagram type.

**Explain a process**

```text
Use explainviz to explain an order flow from payment to shipment.
Include payment failure and cancellation, and label the state transitions.
```

**Compare data**

```text
Use explainviz to compare these monthly sales figures:
Product A: 12, 18, 15, 24; Product B: 10, 14, 20, 22 (January–April, thousands).
Show both trends and make each month's exact values readable.
```

**Explore a 3D shape**

```text
Use explainviz to explain the saddle surface z = (x² − y²) / 4.
Let me rotate it, toggle the coordinate grid, and switch to XY, XZ, and YZ views.
```

**Try an interface**

```text
Use explainviz to make a task-list interface preview.
Let me filter completed tasks and switch between list and grid layouts.
```

Include relevant data, formulas, source files, or design constraints. You can request a static image or interactive HTML, specify a language or theme, and ask for follow-up changes in the same conversation.

## What you receive

- **Static relationships:** Mermaid source that can be used in Markdown and documentation.
- **Static visual explanations:** A rendered image with the editable HTML source retained.
- **Interactive explanations and prototypes:** An HTML file or supported inline preview, plus a preview of its initial state.
- **Supporting explanation:** The key conclusion, assumptions, and limits of the visual.

Standalone HTML can be opened in a browser and edited later. Files that load libraries from a CDN need internet access; 3D views also require WebGL. Inline display, screenshots, and browser verification depend on the assistant's available tools. The skill directs the assistant to report checks it could not perform.

## Repository structure

| File / directory | Purpose |
| --- | --- |
| [SKILL.md](SKILL.md) | Skill entry point and visualization selection rules |
| [references/](references/) | Guidance for diagrams, charts, geometry, and interaction |
| [assets/](assets/) | Reusable HTML examples and document templates |
| [README.md](README.md) / [README.zh-CN.md](README.zh-CN.md) | English and Chinese usage guides |

## When to use it

Use `explainviz` when a picture or an interaction helps you understand something. Ordinary tables, production UI implementation, and publication-grade scientific figures are outside its main scope. Geometry visuals support reasoning; they do not replace mathematical proofs.

## License

[MIT](LICENSE).
