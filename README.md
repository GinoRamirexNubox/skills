# Agent Skills

A collection of agent skills for Claude Code that extend capabilities across the full SDLC — from discovery and planning through development, testing, and deployment.

## Discovery & Planning

Skills for understanding problems and defining scope before writing code.

- **discovery-explore** — Explore a problem space across all repos in the workspace. Read-only, never implements.
  ```
  npx skills@latest add ginoramirex/skills/discovery-explore
  ```
- **discovery-interview** — Guide a structured stakeholder interview to elicit requirements, constraints, and priorities.
  ```
  npx skills@latest add ginoramirex/skills/discovery-interview
  ```
- **grill-me** — Get relentlessly interviewed about a plan or design until every branch of the decision tree is resolved.
  ```
  npx skills@latest add ginoramirex/skills/grill-me
  ```
- **epic-create** — Create a new epic with objectives, acceptance criteria, and initial user story breakdown.
  ```
  npx skills@latest add ginoramirex/skills/epic-create
  ```
- **epic-breakdown** — Decompose an existing epic into implementable user stories with clear scope and repo assignments.
  ```
  npx skills@latest add ginoramirex/skills/epic-breakdown
  ```

## Refinement & Estimation

Skills for turning requirements into actionable specs.

- **refine-technical** — Take a discovery artifact or raw requirement and produce a refined technical spec per repository.
  ```
  npx skills@latest add ginoramirex/skills/refine-technical
  ```
- **refine-estimate** — Estimate complexity and effort of user stories using fibonacci story points with code-based justification.
  ```
  npx skills@latest add ginoramirex/skills/refine-estimate
  ```
- **sprint-plan** — Create a sprint plan by selecting stories from epics, verifying capacity, and organizing the backlog.
  ```
  npx skills@latest add ginoramirex/skills/sprint-plan
  ```
- **adr-create** — Create Architecture Decision Records to document significant technical decisions.
  ```
  npx skills@latest add ginoramirex/skills/adr-create
  ```

## Development

Skills for writing, scaffolding, and reviewing code.

- **code-scaffold** — Scaffold the structure for a cross-repo feature by creating change artifacts (proposal, tasks) in each affected repository.
  ```
  npx skills@latest add ginoramirex/skills/code-scaffold
  ```
- **code-review** — Cross-repo code review focused on API consistency, types, integrations, and testing gaps.
  ```
  npx skills@latest add ginoramirex/skills/code-review
  ```
- **github-ops** — GitHub CLI operations for interacting with repos, PRs, issues, and releases.
  ```
  npx skills@latest add ginoramirex/skills/github-ops
  ```
- **jira** — Natural language interaction with Jira via CLI or Atlassian MCP. View, create, transition, and manage issues.
  ```
  npx skills@latest add ginoramirex/skills/jira
  ```

## Testing & QA

Skills for planning and analyzing test coverage.

- **test-e2e-plan** — Create an end-to-end test plan from epics and technical specifications.
  ```
  npx skills@latest add ginoramirex/skills/test-e2e-plan
  ```
- **test-coverage** — Cross-repo coverage analysis — map requirements vs existing tests and identify gaps.
  ```
  npx skills@latest add ginoramirex/skills/test-coverage
  ```

## Deployment & Release

Skills for managing releases and deployments.

- **deploy-checklist** — Generate a pre-deployment checklist adapted to each repository's tech stack.
  ```
  npx skills@latest add ginoramirex/skills/deploy-checklist
  ```
- **deploy-release** — Multi-repo release management — coordinate versioning, archive changes, and update changelogs.
  ```
  npx skills@latest add ginoramirex/skills/deploy-release
  ```
- **changelog-update** — Update the unified product changelog following Keep a Changelog format in Spanish.
  ```
  npx skills@latest add ginoramirex/skills/changelog-update
  ```

## Onboarding

- **hub-onboard** — Guided workspace onboarding — interactive tour of the hub, repo verification, and orientation.
  ```
  npx skills@latest add ginoramirex/skills/hub-onboard
  ```

## Obsidian & Knowledge Management

Skills for interacting with Obsidian vaults.

- **obsidian-cli** — Interact with Obsidian vaults using the Obsidian CLI to read, create, search, and manage notes.
  ```
  npx skills@latest add ginoramirex/skills/obsidian-cli
  ```
- **obsidian-markdown** — Create and edit Obsidian Flavored Markdown with wikilinks, embeds, callouts, and properties.
  ```
  npx skills@latest add ginoramirex/skills/obsidian-markdown
  ```
- **obsidian-bases** — Create and edit Obsidian Bases (.base files) with views, filters, formulas, and summaries.
  ```
  npx skills@latest add ginoramirex/skills/obsidian-bases
  ```
- **obsidian-quick-note** — Quick capture to the Obsidian vault Inbox. Each entry is tagged with date and time for later processing.
  ```
  npx skills@latest add ginoramirex/skills/obsidian-quick-note
  ```
- **json-canvas** — Create and edit JSON Canvas files (.canvas) with nodes, edges, groups, and connections.
  ```
  npx skills@latest add ginoramirex/skills/json-canvas
  ```

## Tooling & Integrations

- **defuddle** — Extract clean markdown content from web pages using Defuddle CLI, removing clutter to save tokens.
  ```
  npx skills@latest add ginoramirex/skills/defuddle
  ```
- **find-skills** — Discover and install agent skills from the open ecosystem when looking for new capabilities.
  ```
  npx skills@latest add ginoramirex/skills/find-skills
  ```
- **google-workspace-cli** — Interact with all Google Workspace APIs via the `gws` CLI — Drive, Gmail, Calendar, Sheets, Docs, and more.
  ```
  npx skills@latest add ginoramirex/skills/google-workspace-cli
  ```
- **pptx** — Create, read, edit, and manipulate PowerPoint (.pptx) files with template-based editing and programmatic generation.
  ```
  npx skills@latest add ginoramirex/skills/pptx
  ```
