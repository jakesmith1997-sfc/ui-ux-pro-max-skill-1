# UI UX Pro Max (Multi-AI Fork)

Personal fork of [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) adapted for use across multiple AI coding assistants.

**Works with:** Grok · Claude · Cursor · ChatGPT · Windsurf · and other agents that support local skills / custom instructions.

---

## What this skill does

Provides design intelligence for building professional UI/UX:

- **79 searchable UI styles** (50 active)
- **192 product-specific color palettes + reasoning profiles**
- **74 curated font pairings**
- **119 UX guidelines** (accessibility, interaction, layout, forms…)
- **105 icons**, **17 GSAP presets**, **25 chart types**
- **22 technology stacks** (React, Next.js, Vue, Svelte, Flutter, SwiftUI, Tailwind, shadcn, etc.)

The flagship feature is the **Design System Generator** — it analyses a product description and returns a complete, tailored design system (pattern, style, colours, typography, effects, and anti-patterns).

---

## Skill location

The core skill lives at:

```
.claude/skills/ui-ux-pro-max/
```

(or wherever you install/copy it for your AI tool).

Key files:
- `SKILL.md` — main instructions (now multi-AI generic)
- `scripts/search.py` — BM25 search + design-system generator
- `data/` — all CSV / JSON datasets
- `references/` — quick-reference and pro-rules checklists

---

## How to use (any AI)

1. Make sure the skill directory is available to the model.
2. Tell the model the path to the skill (or let it discover it).
3. The model should run the search tool like this:

```bash
python "<SKILL_DIR>/scripts/search.py" "<query>" --domain <domain>
```

or for a full design system:

```bash
python "<SKILL_DIR>/scripts/search.py" "beauty spa wellness" --design-system -p "Serenity Spa"
```

Replace `<SKILL_DIR>` with the actual path on the machine the AI is running on.

### Common paths

| AI          | Typical skill path                                      |
|-------------|---------------------------------------------------------|
| Grok        | `/home/workdir/.grok/skills/ui-ux-pro-max`              |
| Claude Code | `${CLAUDE_PLUGIN_ROOT}/.claude/skills/ui-ux-pro-max`    |
| Cursor      | `.cursor/skills/ui-ux-pro-max` or project-local path    |
| Others      | Wherever you cloned / copied this repo                  |

---

## Original project

This is a personal multi-AI adaptation.  
All credit for the excellent design data and search engine goes to the original authors:

→ https://github.com/nextlevelbuilder/ui-ux-pro-max-skill  
→ https://uupm.cc

License: MIT (same as upstream).

---

## Notes for this fork

- `SKILL.md` has been made **path-agnostic** so it works across Grok, Claude, Cursor, ChatGPT, etc.
- No hard-coded absolute paths remain (except example locations).
- You can safely install or symlink the `.claude/skills/ui-ux-pro-max` folder into whatever skill system your AI uses.
