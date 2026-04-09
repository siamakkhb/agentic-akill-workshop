# Agentic Skills Workshop

A hands-on workshop repository for building, publishing, and managing agentic Claude Code skills using the Skillsmith framework.

---

## Overview

This workshop teaches you how to design and ship Claude Code skills — reusable, trigger-based instructions that extend Claude's behavior for specific workflows. By the end of the workshop, you will have built, validated, and published a fully structured skill to GitHub.

### What you will learn

- How to design a skill with clear triggers, structure, and error handling
- How to validate and publish skills using the Skillsmith CLI
- How to follow the skill authoring conventions (frontmatter, versioning, licensing)
- How to make skills discoverable on GitHub via the `claude-skill` topic

---

## Repository Structure

```
agentic-skills-workshop/
├── exec-email/           # Example skill — executive email drafting for PMs
│   ├── SKILL.md          # Skill definition and documentation
│   ├── README.md         # Installation and usage guide
│   ├── CHANGELOG.md      # Version history
│   ├── LICENSE           # MIT License
│   └── .gitignore
├── agents/               # Agent definitions and configurations
├── skills/               # Additional skill drafts and exercises
├── exercises/            # Workshop exercises and examples
└── README.md             # This file
```

---

## Prerequisites

- [Claude Code](https://claude.ai/code) installed
- Node.js 18+
- Skillsmith CLI:

```bash
npm install -g skillsmith-cli
```

---

## Workshop Exercises

### Exercise 1 — Build Your First Skill

Design a skill from scratch using the Skillsmith authoring conventions.

1. Scaffold a new skill:

```bash
skillsmith author init my-skill --path . -a your-github-username -c communication
```

2. Edit `SKILL.md` — define triggers, structure, tone, and error handling
3. Validate your skill:

```bash
skillsmith validate my-skill/SKILL.md
```

4. Prepare for publishing:

```bash
skillsmith publish my-skill/
```

5. Commit, push, and add the `claude-skill` topic to your GitHub repo

**Reference implementation:** see [`exec-email/`](./exec-email/) for a complete example.

---

## Publishing a Skill

Follow this sequence for every change:

```
validate → publish → commit → push
```

```bash
# 1. Validate
skillsmith validate <skill>/SKILL.md

# 2. Publish (generates .skillsmith-publish.json)
skillsmith publish <skill>/

# 3. Commit
git add <skill>/
git commit -m "your message"

# 4. Push
git push
```

For GitHub auto-discovery, add the `claude-skill` topic to your repository.

---

## Skills in This Repo

| Skill | Description | Status |
|---|---|---|
| [exec-email](./exec-email/) | Draft formal emails from a PM to Amazon L7+ executive audience | Published |

---

## Resources

- [Skillsmith CLI Docs](https://skillsmith.dev)
- [Claude Code](https://claude.ai/code)
- [Claude Code Skills Guide](https://docs.anthropic.com)

---

## License

MIT License — see individual skill directories for their own license files.

## Author

[siamakkhb](https://github.com/siamakkhb)
