# mermaid-diagram

> Generate Mermaid diagrams instead of ASCII art when visualizations are requested

---

## Overview

Claude's default for visualizations is ASCII art — boxes made of `+--+`, pipes, and arrows. These don't render, can't be edited visually, and break in any tool that isn't a plain text editor.

**mermaid-diagram** is a Claude Code skill that intercepts diagram requests and outputs valid [Mermaid](https://mermaid.js.org/) syntax instead. In VS Code with the Mermaid extension installed, these blocks render immediately as interactive diagrams.

### What it does

- Detects diagram intent from natural language (flowchart, sequence, architecture, ER, etc.)
- Selects the most appropriate Mermaid diagram type automatically
- Outputs a fenced ` ```mermaid ` code block with valid syntax — ready to render
- Asks for clarification when the diagram type or entities are ambiguous
- Never falls back to ASCII art

### Who it's for

- Developers and architects documenting systems in VS Code
- Anyone who wants diagrams in Markdown that actually render
- Teams using Mermaid in GitHub, GitLab, Notion, or Confluence

---

## Prerequisites

Install the **Mermaid Preview** extension in VS Code to render diagrams inline:

```
ext install bierner.markdown-mermaid
```

Or search "Mermaid" in the VS Code Extensions panel.

---

## Installation

### Via Skillsmith (recommended)

```bash
skillsmith install siamakkhb/mermaid-diagram
```

### Manual Installation

1. Clone this repository:

```bash
git clone https://github.com/siamakkhb/agentic-skills-workshop.git
```

2. Copy the skill to your Claude skills directory:

```bash
cp -r agentic-skills-workshop/mermaid-diagram ~/.claude/skills/
```

3. Restart Claude Code — the skill will be available immediately.

---

## Quick Start

Trigger the skill using natural language in Claude Code:

| Trigger phrase | Diagram type produced |
|---|---|
| `"draw a flowchart"` | `flowchart TD` |
| `"sequence diagram"` | `sequenceDiagram` |
| `"class diagram"` | `classDiagram` |
| `"ER diagram"` | `erDiagram` |
| `"visualize the architecture"` | `flowchart LR` or `sequenceDiagram` |
| `"map out the flow"` | `flowchart TD` |
| `"git branching diagram"` | `gitGraph` |

### Example prompts

```
draw a sequence diagram for a user login flow with JWT tokens
```

```
diagram the relationship between Order, Product, and Customer tables
```

```
flowchart for our CI/CD pipeline: code → build → test → staging → prod
```

---

## Diagram Types

| Type | Mermaid keyword | Best for |
|---|---|---|
| **Flowchart** | `flowchart TD` / `flowchart LR` | Processes, decisions, step sequences |
| **Sequence** | `sequenceDiagram` | Service interactions, API calls, message flows |
| **Class** | `classDiagram` | OOP structures, data models, inheritance |
| **ER** | `erDiagram` | Database schemas, table relationships |
| **Git** | `gitGraph` | Branching strategies, merge flows |
| **Mind map** | `mindmap` | Topic trees, brainstorming |

---

## Error Handling

The skill will pause and ask rather than guess in these situations:

- **Diagram type is ambiguous** — asks whether you want flow, sequence, or class
- **Entities or actors are unclear** — asks before inventing nodes
- **Diagram would exceed 15 nodes** — asks if you want it split into sub-diagrams

---

## Project Structure

```
mermaid-diagram/
├── SKILL.md          # Skill definition, triggers, and full documentation
├── README.md         # This file
├── CHANGELOG.md      # Version history
├── LICENSE           # MIT License
└── .gitignore        # Git ignore rules
```

---

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/my-improvement`
3. Make your changes and validate: `skillsmith validate SKILL.md`
4. Prepare for publishing: `skillsmith publish`
5. Commit and push, then open a pull request

---

## Changelog

See [CHANGELOG.md](./CHANGELOG.md) for version history.

---

## License

MIT License — see [LICENSE](./LICENSE) for details.

---

## Author

[siamakkhb](https://github.com/siamakkhb) — built with [Skillsmith](https://skillsmith.dev)
