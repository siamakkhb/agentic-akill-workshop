# exec-email

Draft a crisp, structured email from a Product Manager to Amazon L7+ executive audience (Directors, VPs, SVPs)

## Overview

This Claude Code skill helps Product Managers draft formal, high-signal emails to L7+ Amazon leaders (Directors, VPs, SVPs). It enforces a structured format — Subject → TL;DR → Context → Ask/Decision → Next Steps — and calibrates tone based on audience and context.

## Installation

### Via Skillsmith

```bash
skillsmith install siamakkhb/exec-email
```

### Manual Installation

1. Clone or download this repository
2. Copy to your skills directory:

```bash
cp -r exec-email ~/.claude/skills/
```

## Quick Start

1. Install the skill
2. Start Claude Code
3. Trigger with phrases like: `"exec email"`, `"email to VP"`, `"draft for director"`, `"executive update"`

## Documentation

See [SKILL.md](./SKILL.md) for detailed documentation on tone calibration, email structure, and error handling.

## Project Structure

```
exec-email/
├── SKILL.md          # Skill definition and documentation
├── README.md         # This file
├── CHANGELOG.md      # Version history
├── LICENSE           # MIT License
└── .gitignore        # Git ignore rules
```

## License

MIT License — see [LICENSE](./LICENSE) for details.

## Author

[siamakkhb](https://github.com/siamakkhb) — built with [Skillsmith](https://github.com/skillsmith/skillsmith)
