# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

A collection of Claude Code agent skills following the [mattpocock/skills](https://github.com/mattpocock/skills) structure. Each skill is a folder containing a `SKILL.md` and optional reference files. Skills are installable via `npx skills@latest add ginoramirex/skills/<skill-name>`.

## Skill Structure

```
skill-name/
├── SKILL.md           # Main instructions (required, frontmatter with name + description)
├── references/        # Deep-dive docs loaded on demand (optional)
│   └── *.md
└── scripts/           # Utility scripts (optional)
```

### SKILL.md Frontmatter

Every SKILL.md must have YAML frontmatter with at least:
- `name`: kebab-case skill identifier
- `description`: what it does + when to trigger it (max 1024 chars, third person)

### When to Split Files

- SKILL.md should stay under ~100 lines for quick loading
- Move detailed references, examples, or command docs into `references/` subdirectory
- Add utility scripts in `scripts/` when operations are deterministic

## Skill Categories

Skills are organized by SDLC phase:

| Phase | Skills |
|-------|--------|
| Discovery | discovery-explore, discovery-interview |
| Planning | epic-create, epic-breakdown, adr-create |
| Refinement | refine-technical, refine-estimate, sprint-plan |
| Development | code-scaffold, code-review, github-ops, jira |
| Testing | test-e2e-plan, test-coverage |
| Deployment | deploy-checklist, deploy-release, changelog-update |
| Onboarding | hub-onboard |
| Obsidian | obsidian-quick-note |

## Language Convention

All skills use Spanish for their content and output.

## Adding a New Skill

1. Create `skill-name/SKILL.md` with frontmatter
2. Add an entry to `README.md` under the appropriate category
3. Keep SKILL.md concise — split into references if over 100 lines
