---
name: hub-onboard
description: Onboarding guiado al workspace - recorrido interactivo del hub, verificacion de repos y orientacion.
license: MIT
metadata:
  author: nbx-hub
  version: "1.0"
---

Guia interactiva de onboarding al workspace. Presenta la estructura, verifica que los repos son accesibles, explica los comandos disponibles y orienta al usuario segun su rol.

---

## Postura

- **Acogedor**: Bienvenida clara y amigable.
- **Practico**: Muestra lo esencial, no abruma con detalles.
- **Verificador**: Comprueba que todo funciona, no asume.

---

## Pasos

### 1. Bienvenida

Presenta el workspace:
- Proposito del workspace actual.
- Que se puede hacer desde aqui.

### 2. Verificar estructura

Comprueba que existen las carpetas clave del proyecto. Lee el `CLAUDE.md` del proyecto si existe para entender la estructura esperada. Reporta cualquier carpeta faltante.

### 3. Verificar repos

Si existe un registro de repositorios (ej: `registry.yaml`, monorepo con packages, etc.), verificar que las rutas existen en disco y son accesibles. Reportar repos inaccesibles.

### 4. Mostrar comandos disponibles

Presenta los skills y agentes disponibles organizados por fase SDLC:

| Fase | Skill | Que hace |
|------|-------|----------|
| Discovery | `/discovery-explore` | Explorar espacio de problema |
| Discovery | `/discovery-interview` | Entrevista a stakeholders |
| Refinamiento | `/refine-technical` | Refinamiento tecnico |
| Refinamiento | `/refine-estimate` | Estimar story points |
| Planificacion | `/epic-create` | Crear epica |
| Planificacion | `/epic-breakdown` | Descomponer epica |
| Planificacion | `/sprint-plan` | Planificar sprint |
| Codificacion | `/code-scaffold` | Scaffoldear feature |
| Codificacion | `/code-review` | Code review cross-repo |
| Testing | `/test-e2e-plan` | Plan de pruebas E2E |
| Testing | `/test-coverage` | Analisis de cobertura |
| Deploy | `/deploy-checklist` | Checklist pre-deploy |
| Deploy | `/deploy-release` | Gestionar release |
| Transversal | `/changelog-update` | Actualizar changelog |
| Transversal | `/adr-create` | Crear ADR |
| Transversal | `/github-ops` | Operaciones GitHub |
| Transversal | `/jira` | Operaciones Jira |

### 5. Orientar segun contexto

Pregunta al usuario que quiere hacer y sugiere el skill apropiado:
- Recien arrancando? → `/discovery-explore`
- Ya tiene requerimientos? → `/epic-create`
- Ya tiene epica? → `/epic-breakdown` o `/code-scaffold`
- Listo para deploy? → `/deploy-checklist`

---

## Guardariles

1. **No modificar ningun archivo.** Solo lectura y presentacion.
2. **Reportar problemas**, no intentar corregirlos automaticamente.
3. **Ser conciso**: no recitar toda la documentacion, solo orientar.
4. **Adaptar al nivel del usuario**: si ya conoce el workspace, ser breve.
