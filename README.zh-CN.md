# UI 设计提示词

[English](README.md) · **简体中文**

来自 **[UI Atlas](https://ui.ddct.top)** 的免费 UI 设计提示词。每一套风格都是一份完整的设计说明书——12 个章节、25+ 个设计令牌、
逐区块的页面蓝图、组件状态、动效与响应式规则——任何能写前端代码的 AI 都能据此做出同等水准的页面，并附一张用它生成的真实样板页。

适用于 **Claude Code**、**Codex**、**Cursor**、**Trae**、**Copilot**、**Windsurf**，也可以直接粘贴给 Claude、ChatGPT、Gemini、DeepSeek、通义。

## 风格

| 风格 | 分类 | 文件 |
| --- | --- | --- |
| [**Soft Clay**](https://ui.ddct.top/p/soft-clay-fintech) | Fintech | [提示词](styles/soft-clay-fintech/prompt.md) · [技能](skills/ui-soft-clay-fintech/SKILL.md) · [Cursor 规则](cursor-rules/soft-clay-fintech.mdc) · [AGENTS.md](agents-md/AGENTS.soft-clay-fintech.md) · [样板页](https://ui.ddct.top/api/demo/soft-clay-fintech) |
| [**Mist Tone**](https://ui.ddct.top/p/mist-tone-ledger) | Dashboard | [提示词](styles/mist-tone-ledger/prompt.md) · [技能](skills/ui-mist-tone-ledger/SKILL.md) · [Cursor 规则](cursor-rules/mist-tone-ledger.mdc) · [AGENTS.md](agents-md/AGENTS.mist-tone-ledger.md) · [样板页](https://ui.ddct.top/api/demo/mist-tone-ledger) |

更多风格（SaaS、数据看板、电商、杂志等）见 **[ui.ddct.top](https://ui.ddct.top/explore)**。

## 安装

**Claude Code（插件）**

```text
/plugin marketplace add qianye60/ui-design-prompts
/plugin install ui-design-prompts@ui-design-prompts
```

之后直接说：“用 Soft Clay 风格重做我的落地页。”Claude 会自动加载对应技能。
也可以只复制一个技能：`cp -r skills/ui-soft-clay-fintech ~/.claude/skills/`

**Cursor**：`cp cursor-rules/soft-clay-fintech.mdc .cursor/rules/`

**Codex / Copilot / Windsurf 等读取 AGENTS.md 的工具**：`cat agents-md/AGENTS.soft-clay-fintech.md >> AGENTS.md`

**任意对话 AI**：打开 `styles/<风格>/prompt.md`，全文复制后连同需求一起发送。

**MCP（整座风格库）**：接入 UI Atlas 的 MCP 服务，让 AI 自己搜索和读取所有风格，见 [https://ui.ddct.top/use](https://ui.ddct.top/use)。

## 许可

本仓库的提示词与样板页采用 [CC BY 4.0](LICENSE) 许可。转载或改编时请注明 **UI Atlas** 并附上 https://ui.ddct.top 链接。

样板页中的品牌、文案和产品均为虚构。
