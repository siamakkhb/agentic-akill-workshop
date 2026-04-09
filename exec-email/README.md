# exec-email

> Draft crisp, structured emails from a Product Manager to Amazon L7+ executive audience (Directors, VPs, SVPs)

---

## Overview

Writing emails to senior leaders is one of the highest-leverage — and most unforgiving — communication tasks a Product Manager faces. A poorly structured email to a VP or Director can delay decisions, damage credibility, or simply get ignored.

**exec-email** is a Claude Code skill that helps PMs consistently produce high-signal executive communications. It enforces a battle-tested structure, calibrates tone to the audience, and catches common mistakes before they reach the inbox of a senior leader.

### What it does

- Drafts formal emails structured as: **Subject → TL;DR → Context → Ask/Decision → Next Steps**
- Calibrates tone based on audience (Director, VP, SVP) and context (escalation, decision request, update, post-mortem)
- Flags vague asks, multiple conflicting requests, and missing context before drafting
- Sharpens existing drafts — tightens language, removes filler, enforces a single clear ask
- Surfaces assumptions explicitly when input is incomplete, rather than fabricating context

### Who it's for

- Product Managers communicating up to L7+ Amazon leaders
- PMs preparing launch updates, escalations, risk flags, decision requests, or incident post-mortems
- Anyone who needs to write executive emails quickly without sacrificing quality

---

## Installation

### Via Skillsmith (recommended)

```bash
skillsmith install siamakkhb/exec-email
```

### Manual Installation

1. Clone this repository:

```bash
git clone https://github.com/siamakkhb/agentic-akill-workshop.git
```

2. Copy the skill to your Claude skills directory:

```bash
cp -r agentic-akill-workshop/exec-email ~/.claude/skills/
```

3. Restart Claude Code — the skill will be available immediately.

---

## Quick Start

Once installed, trigger the skill using natural language in Claude Code:

| Trigger phrase | Use case |
|---|---|
| `"exec email"` | General executive email |
| `"email to VP"` | VP-level communication |
| `"draft for director"` | Director-level communication |
| `"executive update"` | Status or launch update |
| `"email to SVP"` | SVP-level communication |
| `"write to leadership"` | Senior leadership communication |
| `"C-suite email"` | C-suite communication |

### Example prompt

```
exec email — to our Director, subject is a 2-month project delay due to attrition,
purpose is to get alignment, key points: lost 2 engineers, SDM is backfilling but
no timeline yet, background: critical project for a major client
```

---

## Email Structure

Every email produced by this skill follows this format:

| Section | Purpose |
|---|---|
| **Subject** | Signals urgency and required action before the email is opened |
| **TL;DR** | 3-sentence max — situation + ask or impact, written to stand alone |
| **Context** | Only what's needed to understand the situation — no padding |
| **Ask / Decision** | One primary ask, unambiguous, with a deadline if one exists |
| **Next Steps** | `[Owner] will [action] by [date]` — always includes the PM's own step |

---

## Tone Guidelines

| Tone | When to use | Example opening |
|---|---|---|
| **Formal (default)** | Decision requests, escalations, risk flags, incident summaries | *"I am writing to flag a risk to our Q3 launch timeline..."* |
| **Warm but crisp** | Recognition, team wins, known collaborators | *"Wanted to share a quick win the team shipped this week..."* |
| **Never** | Hedging language, filler phrases, passive voice when action is needed | *"Hope this finds you well..."* |

---

## Error Handling

The skill will pause and ask rather than guess in these situations:

- **Audience not specified** — tone and framing depend entirely on who the recipient is
- **Purpose is vague** — exec emails require one clear sentence on why the email is being sent
- **No background provided** — the skill will not fabricate context; it asks for at least one source
- **Multiple asks detected** — will flag and recommend splitting or ranking asks explicitly

---

## Project Structure

```
exec-email/
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
