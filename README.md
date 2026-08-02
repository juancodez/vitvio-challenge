# Bit.Bio — VITVIO Whiteboard Challenge

This repository is part of the **VITVIO Whiteboard Challenge** — a design sprint to build a live, clickable prototype from scratch using Claude Code as the primary design-to-code tool.

## What this is

A structured design project scaffold for **Bit.Bio**, a biotech product concept. The goal is to go from brief to interactive prototype in one week, using a file structure that keeps Claude Code, Figma, and the codebase in sync at all times.

## Stack

- **Design** — Figma (components, variants, prototype flows)
- **Tokens** — `design-tokens.json` (single source of truth for color, type, spacing)
- **Components** — `src/components/` (HTML/CSS reference implementations)
- **AI assistant** — Claude Code with project-aware context via `CLAUDE.md`

## Project structure

```
Bit.Bio/
├── CLAUDE.md               # Brief Claude reads every session
├── .mcp.json               # Figma, Notion, Drive connections
├── design-tokens.json      # Color, typography, spacing, radius
├── .claude/
│   ├── rules/              # Conventions loaded when relevant
│   ├── skills/             # Repeatable workflows
│   └── commands/           # Custom slash commands
├── src/components/         # UI components Claude reads and edits
├── public/images/          # Assets so prototypes don't break
└── reference/              # Real screens Claude studies for context
```

## Challenge context

> Build a live prototype for Bit.Bio — a biotech/life-sciences product — ready for stakeholder review.

This is a whiteboard-to-prototype sprint. No pre-existing codebase. Claude Code handles scaffolding, token management, and component generation while the designer drives decisions.

---

**Designer:** Juan Gomez-Vara — Product Designer
