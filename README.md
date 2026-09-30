# explainviz

[![skills.sh](https://skills.sh/b/liujy20/explainviz)](https://skills.sh/liujy20/explainviz)

Choose the smallest useful visual representation for an explanation. `explainviz` routes requests to Mermaid diagrams, HTML-based charts, maps, geometry explainers, interactive fragments, or interface prototypes.

## Install

Install from the public GitHub repository with the skills CLI:

```bash
npx skills add liujy20/explainviz
```

To install only this skill when the repository contains more than one skill:

```bash
npx skills add liujy20/explainviz --skill explainviz
```

To preview the available skill without installing it:

```bash
npx skills add liujy20/explainviz --list
```

## Discovery on skills.sh

The public source repository is [liujy20/explainviz](https://github.com/liujy20/explainviz). According to the [skills.sh FAQ](https://skills.sh/docs/faq), skills are listed automatically through anonymous installation telemetry from the skills CLI.

After the repository is published, install the skill with telemetry enabled:

```bash
npx skills add liujy20/explainviz --skill explainviz
```

Keep `DISABLE_TELEMETRY` and `DO_NOT_TRACK` unset for that installation. Listing skills with `--list` verifies discovery but does not install the skill. Allow time for processing and caches to refresh, then search with:

```bash
npx skills find explainviz
```

The expected skill page is [skills.sh/liujy20/explainviz/explainviz](https://skills.sh/liujy20/explainviz/explainviz). Listing is subject to platform processing; publishing a repository alone does not guarantee immediate search visibility.

## What it provides

- Mermaid source for static nodes and relationships.
- Browser-based visualizations for changing data, maps, and time-based views.
- D3-based geometry and topology explainers.
- Interactive HTML fragments and interface mockups.
- Guidance for delivering accessible, inspectable standalone HTML.

The skill definition is in [`SKILL.md`](SKILL.md). Supporting guidance and examples live in [`references/`](references/) and [`assets/`](assets/).

## Repository layout

```text
SKILL.md                 Skill definition and routing instructions
references/              Detailed guidance for each visualization route
assets/examples/         Reusable HTML examples
```

## Compatibility

The skill follows the shared Agent Skills format and can be installed for Codex, Claude Code, Cursor, and other agents supported by the skills CLI.

## License

MIT. See [`LICENSE`](LICENSE).
