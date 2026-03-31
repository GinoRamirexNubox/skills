# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Que es este repo

Coleccion de skills para Claude Code siguiendo la estructura de [mattpocock/skills](https://github.com/mattpocock/skills). Cada skill es una carpeta con un `SKILL.md` y archivos de referencia opcionales. Se instalan via `npx skills@latest add GinoRamirexNubox/skills/<skill-name>`.

## Estructura de un skill

```
skill-name/
├── SKILL.md           # Instrucciones principales (requerido, frontmatter con name + description)
├── references/        # Docs detallados cargados bajo demanda (opcional)
│   └── *.md
└── scripts/           # Scripts utilitarios (opcional)
```

### Frontmatter de SKILL.md

Todo SKILL.md debe tener frontmatter YAML con al menos:
- `name`: identificador en kebab-case
- `description`: que hace + cuando activarlo (max 1024 chars, tercera persona)

Campos opcionales usados en la mayoria de skills:
- `license`: e.g. `MIT`
- `metadata.author`: e.g. `nbx-hub`
- `metadata.version`: e.g. `"1.0"`

### Cuando separar archivos

- SKILL.md debe mantenerse bajo ~100 lineas para carga rapida
- Mover referencias detalladas, ejemplos o docs de comandos a `references/`
- Agregar scripts utilitarios en `scripts/` cuando las operaciones son deterministas

## Categorias

Skills organizados por fase SDLC:

| Fase | Skills |
|------|--------|
| Descubrimiento | discovery-explore, discovery-interview |
| Planificacion | epic-create, epic-breakdown, adr-create |
| Refinamiento | refine-technical, refine-estimate, sprint-plan |
| Desarrollo | code-scaffold, code-review, github-ops, jira |
| Testing | test-e2e-plan, test-coverage |
| Despliegue | deploy-checklist, deploy-release, changelog-update |
| Onboarding | hub-onboard |
| Obsidian | obsidian-quick-note |

## Convencion de idioma

Todos los skills usan espanol para su contenido y salida. Esto incluye el campo `description` del frontmatter.

**Excepcion conocida**: `jira/SKILL.md` tiene description en ingles — debe corregirse.

## Validacion

- No hay build, lint ni tests automatizados. La validacion es manual: verificar frontmatter valido, lineas < 100, y que el README tenga la entrada.
- `github-ops` (164 lineas) y `jira` (195 lineas) exceden el limite de 100 lineas y deberian refactorizarse moviendo contenido a `references/`.
- Solo `jira/` usa `references/` actualmente (`commands.md`, `mcp.md`).

## Agregar un nuevo skill

1. Crear `skill-name/SKILL.md` con frontmatter (incluir `license` y `metadata`)
2. Agregar entrada en `README.md` bajo la categoria correspondiente
3. Mantener SKILL.md conciso — separar en references si supera 100 lineas
