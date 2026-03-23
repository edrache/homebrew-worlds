# Homebrew Worlds

A collection of tabletop RPG settings, playbooks, and adventure generators built on the **Homebrew World** system — a streamlined ruleset derived from Dungeon World / Powered by the Apocalypse.

This repository is designed to work with any LLM. It includes ready-to-play settings, conversion tools, and AI skills for generating new content.

---

## Settings

Each setting includes playbooks for every class (EN + PL), optional moves, and a d20 adventure generator.

| Setting | Playbooks | Languages |
|---------|-----------|-----------|
| [Diablo 2](Settings/Diablo_2/) | 5 | EN, PL |
| [Dolmenwood](Settings/Dolmenwood/) | 7 | EN, PL |
| [Dolmenwood – Humans](Settings/Dolmenwood-Humans/) | 9 | EN, PL |
| [Earthdawn](Settings/Earthdawn/) | 5 | EN, PL |
| [Frieren](Settings/Frieren/) | 5 | EN, PL |
| [Sinners](Settings/Sinners/) | 5 | EN, PL |
| [Star Trek TNG](Settings/Star_Trek_TNG/) | 5 | EN, PL |
| [Star Wars](Settings/Star_Wars/) | 5 | EN |
| [Star Wars – Jedi](Settings/Star_Wars_Jedi/) | 5 | EN, PL |
| [The Studio](Settings/The_Studio/) | 5 | EN, PL |

Each setting lives in `Settings/<Name>/en/` and `Settings/<Name>/pl/`.

---

## System Overview

**Homebrew World** is a lightweight PbtA system. Key rules:

- **Stat array:** +2, +1, +1, 0, 0, -1 (player-distributed)
- **HP:** fixed per class (not CON-based)
- **Equipment:** gear slots + Supplies
- **Drives:** replace Alignments — complete them to gain XP
- **Moves:** defined by tags (`messy`, `forceful`, `magical`, `reach`, etc.)

### Playbook structure

Every `Playbook_<Class>.md` contains:
Names · Looks · Background (4 options) · HP · Damage Die · Starting Stats · Starting Moves · Advances · Drives · Equipment

### Adventure Generator

Each setting includes `adventure.md` — six d20 tables that generate a complete adventure premise (action, location, goal, party task, threats, antagonist).

---

## Tools (Skills)

The `Skills/` directory contains LLM-ready tools for working with this system. Each skill has a `SKILL.md` with full instructions — pass it to your LLM before starting the task.

| Skill | Purpose |
|-------|---------|
| `homebrew-world-designer` | Design new settings and playbooks from scratch |
| `homebrew-playbook-sheet` | Convert Markdown playbooks → PDF (A4 landscape, B&W) |
| `homebrew-web-presenter` | Generate an interactive HTML page from a setting folder |
| `homebrew-world-publisher` | Publish the full static hub site |
| `pdf-to-md` | Extract and clean text from a PDF into Markdown |
| `pdf-translator-pl` | Translate EN PDF → PL Markdown → PL PDF |
| `rpg-translator` | RPG terminology reference PL/EN |
| `merge-pdfs` | Merge multiple PDFs into a single file |

### Using with Claude Code

```
/homebrew-world-designer
```

Skills in `Skills/` are Claude Code–compatible. The `.skill` files can be loaded directly.

### Using with OpenAI Codex or other LLMs

Read `AGENTS.md` for project context, then open the relevant `Skills/<name>/SKILL.md` and follow its instructions.

---

## Static Site

The `site/` directory contains a deployable static website presenting all settings. Each setting page includes:
- Interactive playbook viewer with PL/EN switcher
- Downloadable PDF bundles
- Adventure Generator with random roll

Design system: **Manrope** (UI) + **Cormorant Garamond** (headings), warm amber accent, glass-card layout.

---

## Repository Structure

```
Homebrew-worlds/
├── Settings/          # All settings (Markdown source files)
├── Skills/            # LLM tools and scripts
├── site/              # Static HTML site with PDFs
├── PDF/               # Working directory for PDF generation
├── CLAUDE.md          # Instructions for Claude Code
└── AGENTS.md          # Instructions for OpenAI Codex and other LLMs
```

---

## License

Settings and playbooks are fan-made content for personal use. **Homebrew World** is created by [Jeremy Strandberg](https://spoutinglore.blogspot.com/2018/07/homebrew-world.html). Built on [Dungeon World](https://dungeon-world.com/) (CC BY 3.0) / Powered by the Apocalypse.
