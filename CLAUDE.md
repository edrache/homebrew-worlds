# Homebrew Worlds – CLAUDE.md

## Project Goal

Repository for creating **settings, playbooks, and adventures** based on the **Homebrew World** system (built on Dungeon World / Powered by the Apocalypse). The project is public on GitHub – anyone can download and use it with any LLM.

Contents:
- **Settings/** – ready-made settings (playbooks + adventure generators), in Polish and English
- **Skills/** – tools (Claude / other LLM skills) for creating, translating, and publishing settings
- **site/** – static HTML page presenting the settings
- **PDF/** – generated PDF files

---

## Directory Structure

```
Homebrew-worlds/
├── Settings/
│   ├── <Setting_Name>/
│   │   ├── en/
│   │   │   ├── Playbook_<Class>.md
│   │   │   ├── Optional_Moves.md
│   │   │   └── adventure.md
│   │   └── pl/
│   │       ├── Playbook_<Class>.md
│   │       ├── Optional_Moves.md
│   │       └── adventure.md
├── Skills/
│   ├── homebrew-world-designer/    # Setting and playbook design
│   ├── homebrew-playbook-sheet/    # MD → PDF conversion (2 pages/playbook)
│   ├── homebrew-web-presenter/     # HTML page generation from playbook MD files
│   ├── homebrew-world-publisher/   # Publishing the static hub page
│   ├── pdf-to-md/                  # PDF → Markdown extraction
│   ├── pdf-translator-pl/          # PDF translation EN → PL
│   ├── rpg-translator/             # RPG terminology PL/EN
│   └── merge-pdfs/                 # Merging multiple PDFs into one file
├── site/
│   ├── index.html                  # Hub – list of all settings
│   ├── style.css                   # Shared stylesheet
│   └── <setting-name>/             # HTML page for a given setting
└── PDF/                            # Generated PDF files
```

---

## Homebrew World System Mechanics

### Playbook – Required Structure

Each `Playbook_<Class>.md` file must contain:

1. **Header** – class name (PL + EN)
2. **Names** – lists of names grouped culturally/by species
3. **Looks** – 5–7 choice categories (species, clothing, weapon, etc.)
4. **Background** – 4 options with mechanical benefits (one to choose)
5. **HP** – fixed value (class-specific)
6. **Damage Die** – d6/d8/d10/d12
7. **Starting Stats** – statistics: `+2, +1, +1, 0, 0, -1` (distributed by player)
8. **Starting Moves** – 4–6 moves with tag mechanics
9. **Advances** – 6 expansion moves (to unlock)
10. **Drives** – 4 goals granting XP (replacing Alignments)
11. **Equipment** – slots + "Supplies"

### Key Mechanical Rules

- Stat array: `+2, +1, +1, 0, 0, -1` (always the same values)
- HP is fixed per class (does not depend on CON at character creation)
- Equipment: "Undefined gear" slots + always "Supplies"
- Drives replace Alignments – they grant XP
- Moves: tags define mechanics (advantage, GM reaction, etc.)
- Prep: 7 encounters, 3 sensory details, 1 trait per NPC

### Adventure Generator (adventure.md)

6 d20 tables generating an adventure premise:
1. Action and location
2. Geographic setting
3. Goal/object
4. Party's task
5. Minor threats
6. Main antagonist

---

## Settings in the Project

| Directory | Title | Playbooks | Languages |
|-----------|-------|-----------|-----------|
| Diablo_2 | Diablo 2 | 5 | PL, EN |
| Dolmenwood | Dolmenwood | 7–8 | PL, EN |
| Dolmenwood-Humans | Dolmenwood (Humans) | 9–11 | PL, EN |
| Earthdawn | Earthdawn | 5–6 | PL, EN |
| Frieren | Frieren | 5 | PL, EN |
| Sinners | Sinners | 5 | PL, EN |
| Star_Trek_TNG | Star Trek TNG | 10 | PL, EN |
| Star_Wars | Star Wars | 5 | EN |
| Star_Wars_Jedi | Star Wars Jedi | 10 | PL, EN |
| The_Studio | The Studio | 5–10 | PL, EN |

---

## Tools (Skills)

### homebrew-world-designer
Main skill for designing settings. Generates:
- Setting premise (Theme, Stakes, Threats, Urgency, Complications)
- Playbooks with full mechanics
- Adventure generators
- Output: separate Markdown files

### homebrew-playbook-sheet
Converts `Playbook_*.md` → compact PDF (max 2 pages, A4 landscape, B&W).
- If `Optional_Moves.md` exists: additional appendix page
- Folder as input: merges playbooks into a single PDF book

### homebrew-web-presenter
Generates an interactive HTML page from a playbooks folder.
- Design consistent with the hub (Manrope + Cormorant Garamond, amber accents)
- Sidebar navigation, PL/EN language switcher
- Adventure Generator tab with random rolls

### homebrew-world-publisher
Publishes the static hub page (site/).
- **IMPORTANT:** Always build ALL settings before deploying (rsync --delete removes unbuilt ones)

### pdf-to-md / pdf-translator-pl / rpg-translator
Translation pipeline: PDF EN → Markdown → terminology translation → PDF PL.

---

## Design System (site/)

- **Fonts:** Manrope (UI), Cormorant Garamond (headings)
- **Accent:** warm amber
- **Cards:** glass/frosted effect
- **Layout:** responsive, sidebar navigation
- **Default language:** Polish

---

## Naming Conventions

- Playbook files: `Playbook_<ClassName>.md` (underscores, CamelCase)
- Setting directories: `Setting_Name` (underscores)
- Directories in site/: `setting-name` (kebab-case)
- Languages: subdirectories `en/` and `pl/`

---

## Notes for LLM

- Use English in all files by default, unless a different language is requested
- Code and variable names always in English
- Playbook content: language depends on the subdirectory (`en/` or `pl/`)
- When creating a new setting: `en/` first, then `pl/` (or in parallel)
- Skill `homebrew-world-designer` contains reference PDFs with system rules
- When modifying site/ – always check consistency with `style.css`
