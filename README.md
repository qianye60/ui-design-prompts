# UI Design Prompts

**English** · [简体中文](README.zh-CN.md)

Free, production-grade UI design prompts from **[UI Atlas](https://ui.ddct.top)** — each style is a complete design brief
(12 chapters, 25+ design tokens, a section-by-section page blueprint, component states, motion and responsive rules)
that any code-writing AI can follow, plus a real demo page built from it.

Use them in **Claude Code**, **Codex**, **Cursor**, **Copilot**, **Windsurf**, **Trae**, or paste them into Claude, ChatGPT, Gemini, v0 and Lovable.

## Styles

| Style | Look | Category | Files |
| --- | --- | --- | --- |
| [**Soft Clay**](https://ui.ddct.top/p/soft-clay-fintech) | Claymorphism × pastel candy colors, a playful fintech app landing page | Fintech | [prompt](styles/soft-clay-fintech/prompt.md) · [skill](skills/ui-soft-clay-fintech/SKILL.md) · [Cursor rule](cursor-rules/soft-clay-fintech.mdc) · [AGENTS.md](agents-md/AGENTS.soft-clay-fintech.md) · [live demo](https://ui.ddct.top/api/demo/soft-clay-fintech) |
| [**Mist Tone**](https://ui.ddct.top/p/mist-tone-ledger) | A pale-grey order book: one blue pencil, one black stamp. | Dashboard | [prompt](styles/mist-tone-ledger/prompt.md) · [skill](skills/ui-mist-tone-ledger/SKILL.md) · [Cursor rule](cursor-rules/mist-tone-ledger.mdc) · [AGENTS.md](agents-md/AGENTS.mist-tone-ledger.md) · [live demo](https://ui.ddct.top/api/demo/mist-tone-ledger) |

More styles (SaaS, dashboards, commerce, editorial and more) are at **[ui.ddct.top](https://ui.ddct.top/explore)**.

## Install

### Claude Code (plugin)

```text
/plugin marketplace add qianye60/ui-design-prompts
/plugin install ui-design-prompts@ui-design-prompts
```

Then ask: *“Rebuild my landing page in the Soft Clay style.”* Claude loads the matching skill automatically.

Or copy a single skill: `cp -r skills/ui-soft-clay-fintech ~/.claude/skills/`

### Cursor

Copy a rule into your project: `cp cursor-rules/soft-clay-fintech.mdc .cursor/rules/`

### Codex, Copilot, Windsurf and other AGENTS.md tools

Append a style to your project's `AGENTS.md`: `cat agents-md/AGENTS.soft-clay-fintech.md >> AGENTS.md`

### Any chat AI

Open `styles/<style>/prompt.md`, copy everything, paste it with your request.

### MCP (whole library)

Connect the UI Atlas MCP server to let your agent search and read every style itself — see [https://ui.ddct.top/use](https://ui.ddct.top/use?lang=en).

## Previews

### Soft Clay

[![Soft Clay — Claymorphism × pastel candy colors, a playful fintech app landing page](https://ui.ddct.top/og/soft-clay-fintech.jpg)](https://ui.ddct.top/p/soft-clay-fintech)

- A floating pure-CSS phone with coins
- A tilted peach highlighter stroke
- Clay-textured slider calculator

### Mist Tone

[![Mist Tone — A pale-grey order book: one blue pencil, one black stamp.](https://ui.ddct.top/og/mist-tone-ledger.jpg)](https://ui.ddct.top/p/mist-tone-ledger)

- Depth by tone only, no borders or shadows
- Big figure with muted 14px unit
- Split-label filter pills with hairline
- One black action per context

## License

Prompts and demo pages in this repository are licensed under [CC BY 4.0](LICENSE).
Please credit **UI Atlas** with a link to https://ui.ddct.top when you share or adapt them.

Generated from [UI Atlas](https://ui.ddct.top). Brands, copy and products in the demos are fictional.
