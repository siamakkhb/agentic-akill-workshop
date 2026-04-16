---
name: mermaid-diagram
description: Generate Mermaid diagrams instead of ASCII art when visualizations are requested
version: 1.0.0
author: siamakkhb
license: MIT
tags: [mermaid, diagram, visualization, flowchart, vscode]
repository: https://github.com/siamakkhb/agentic-skills-workshop
compatibility: [claude-code, cursor, claude]
---

## When to Use
- Keyword trigger: "diagram", "draw", "chart", "flowchart", "sequence diagram", "visualize", "map out", "architecture diagram", "draw me", "show the flow", "class diagram", "ER diagram", "graph"
- Context trigger: any request where Claude would otherwise produce ASCII art (boxes with `+--+`, pipes `|`, arrows `→`, or similar character art)
- Workflow trigger: when explaining system architecture, data flows, process steps, class relationships, database schemas, or branching strategies

## Quick Reference

### Generate a New Diagram
Identify the diagram type from context, then output a fenced ` ```mermaid ` code block with valid Mermaid syntax.
Never produce ASCII art — always use Mermaid, even for simple two-node relationships.
VS Code with the Mermaid extension will render the block automatically.

### Choose the Right Diagram Type
Match the diagram type to the content:
- **flowchart TD** — processes, decisions, workflows, step sequences
- **sequenceDiagram** — service interactions, API calls, message flows between actors
- **classDiagram** — OOP structures, data models, inheritance hierarchies
- **erDiagram** — database schemas, table relationships
- **gitGraph** — branching strategies, merge flows
- **mindmap** — brainstorming, topic trees, concept hierarchies

### Improve an Existing Diagram
Check: Are node labels concise (≤ 5 words)? Are edge labels descriptive? Is the diagram type the best fit? Would splitting into sub-diagrams improve clarity?

## Full Documentation

### Diagram Type Selection
Choose the most precise type available. Do not default to flowchart when a more specific type fits:
- **flowchart TD** (top-down) or **flowchart LR** (left-right): use LR for wide, linear pipelines; TD for hierarchies and trees
- **sequenceDiagram**: always use for showing message passing between named actors — never use flowchart for this
- **classDiagram**: use when showing attributes, methods, and relationships (inheritance, composition, association)
- **erDiagram**: use for database-oriented schemas; supports cardinality notation (`||--o{`)
- **gitGraph**: use only for git branching — commit, branch, merge, checkout operations
- **mindmap**: use for radial topic expansion, not for directed flows

### Syntax Rules
1. Output diagram inside a fenced ` ```mermaid ` code block — nothing outside it
2. Node IDs: use camelCase or UPPER_SNAKE, no spaces (e.g., `userService`, `AUTH_DB`)
3. Node labels: wrap in quotes if they contain spaces — `A["User Login"]`
4. Edge labels: use `-->|label|` syntax for labeled edges
5. Keep labels ≤ 5 words — truncate or abstract if longer
6. Do not nest diagram types — one diagram per block
7. Valid Mermaid syntax only — test mentally before outputting

### Output Format
Always produce exactly this structure:

` ```mermaid `
[diagram type and content]
` ``` `

Follow the block immediately with a one-sentence explanation of what the diagram shows, if it would help the user.

### Error Handling
- **Diagram type is ambiguous:** Do not guess. Ask: "Should this be a flow, sequence, or class diagram?"
- **Entities or actors are unclear:** Ask before inventing nodes — fabricated nodes cause incorrect diagrams
- **Diagram would exceed 15 nodes:** Ask if the user wants it split into multiple focused diagrams
- **Request is for ASCII art explicitly:** Redirect — output Mermaid instead and note that VS Code will render it
- **Syntax would be invalid:** Simplify the diagram rather than produce broken Mermaid — flag what was omitted
