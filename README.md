# Agent Skills

Coleccion de skills para Claude Code que extienden capacidades a lo largo de todo el SDLC — desde descubrimiento y planificacion hasta desarrollo, testing y despliegue.

## Descubrimiento y Planificacion

Skills para entender problemas y definir alcance antes de escribir codigo.

- **discovery-explore** — Explorar un espacio de problema a traves de todos los repos del workspace. Solo lectura, nunca implementa.
  ```
  npx skills@latest add ginoramirex/skills/discovery-explore
  ```
- **discovery-interview** — Guiar una entrevista estructurada a stakeholders para elicitar requerimientos, restricciones y prioridades.
  ```
  npx skills@latest add ginoramirex/skills/discovery-interview
  ```
- **epic-create** — Crear una nueva epica con objetivos, criterios de aceptacion y desglose inicial de historias de usuario.
  ```
  npx skills@latest add ginoramirex/skills/epic-create
  ```
- **epic-breakdown** — Descomponer una epica existente en historias de usuario implementables con scope claro y asignaciones por repo.
  ```
  npx skills@latest add ginoramirex/skills/epic-breakdown
  ```

## Refinamiento y Estimacion

Skills para convertir requerimientos en especificaciones accionables.

- **refine-technical** — Tomar un artefacto de descubrimiento o requerimiento bruto y producir una especificacion tecnica refinada por repositorio.
  ```
  npx skills@latest add ginoramirex/skills/refine-technical
  ```
- **refine-estimate** — Estimar complejidad y esfuerzo de historias de usuario usando story points fibonacci con justificacion basada en codigo.
  ```
  npx skills@latest add ginoramirex/skills/refine-estimate
  ```
- **sprint-plan** — Crear un plan de sprint seleccionando historias de epicas, verificando capacidad y organizando el backlog.
  ```
  npx skills@latest add ginoramirex/skills/sprint-plan
  ```
- **adr-create** — Crear Architecture Decision Records para documentar decisiones tecnicas significativas.
  ```
  npx skills@latest add ginoramirex/skills/adr-create
  ```

## Desarrollo

Skills para escribir, scaffoldear y revisar codigo.

- **code-scaffold** — Scaffoldear la estructura de un feature cross-repo creando artefactos de cambio (proposal, tasks) en cada repositorio afectado.
  ```
  npx skills@latest add ginoramirex/skills/code-scaffold
  ```
- **code-review** — Revision de codigo cross-repo enfocada en consistencia de APIs, tipos, integraciones y gaps de testing.
  ```
  npx skills@latest add ginoramirex/skills/code-review
  ```
- **github-ops** — Operaciones de GitHub CLI (gh) para interactuar con repos, PRs, issues y releases.
  ```
  npx skills@latest add ginoramirex/skills/github-ops
  ```
- **jira** — Interaccion con Jira via CLI o Atlassian MCP. Ver, crear, transicionar y gestionar issues.
  ```
  npx skills@latest add ginoramirex/skills/jira
  ```

## Testing y QA

Skills para planificar y analizar cobertura de tests.

- **test-e2e-plan** — Crear plan de pruebas end-to-end a partir de epicas y especificaciones tecnicas.
  ```
  npx skills@latest add ginoramirex/skills/test-e2e-plan
  ```
- **test-coverage** — Analisis de cobertura cross-repo — mapea requerimientos vs tests existentes e identifica gaps.
  ```
  npx skills@latest add ginoramirex/skills/test-coverage
  ```

## Despliegue y Release

Skills para gestionar releases y deployments.

- **deploy-checklist** — Generar checklist de pre-deployment adaptado al tech stack de cada repositorio involucrado.
  ```
  npx skills@latest add ginoramirex/skills/deploy-checklist
  ```
- **deploy-release** — Gestion de release multi-repo — coordinar versionado, archivar cambios y actualizar changelogs.
  ```
  npx skills@latest add ginoramirex/skills/deploy-release
  ```
- **changelog-update** — Actualizar el changelog unificado del producto siguiendo el formato Keep a Changelog.
  ```
  npx skills@latest add ginoramirex/skills/changelog-update
  ```

## Onboarding

- **hub-onboard** — Onboarding guiado al workspace — recorrido interactivo del hub, verificacion de repos y orientacion.
  ```
  npx skills@latest add ginoramirex/skills/hub-onboard
  ```

## Obsidian

- **obsidian-quick-note** — Captura rapida al Inbox del vault Obsidian. Cada entrada se tagea con fecha y hora para proceso posterior.
  ```
  npx skills@latest add ginoramirex/skills/obsidian-quick-note
  ```
