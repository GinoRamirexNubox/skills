---
name: deploy-checklist
description: Generar checklist de pre-deployment adaptado al tech stack de cada repositorio involucrado.
license: MIT
metadata:
  author: nbx-hub
  version: "1.0"
---

Genera un checklist de verificacion pre-deployment para una release, adaptado al tech stack especifico de cada repo involucrado. Verifica que todo este listo antes de desplegar a produccion.

---

## Entrada

- Release o feature a desplegar.
- Repos involucrados (o detectar desde epica).

---

## Pasos

### 1. Identificar repos y tech stacks

Para cada repo involucrado, identifica:
- Tech stack (React, NestJS, Java, .NET, etc.).
- Package manager (pnpm, npm, gradle, dotnet).
- Tipo de deploy (frontend, backend, BFF, microservicio).

### 2. Generar checklist por repo

Adapta las verificaciones al tech stack:

**Frontend (React/Next.js)**:
- [ ] Build de produccion exitoso
- [ ] Variables de entorno de produccion configuradas
- [ ] Assets optimizados (imagenes, bundles)
- [ ] Feature flags configurados

**Backend (NestJS/Java/.NET)**:
- [ ] Tests pasan en CI
- [ ] Migraciones de base de datos preparadas
- [ ] Health checks configurados
- [ ] Variables de entorno de produccion

**General (todos los repos)**:
- [ ] Code review aprobado
- [ ] Branch actualizado con main
- [ ] Sin secrets en el codigo
- [ ] Changelog actualizado
- [ ] Documentacion actualizada

### 3. Verificar dependencias entre repos

- Orden de deploy (backend antes que frontend, migraciones antes que servicios).
- Compatibilidad de versiones de APIs.
- Feature flags para deploy gradual.

### 4. Generar documento

```markdown
# Checklist Pre-Deploy: <release>

**Fecha**: YYYY-MM-DD
**Repos**: repo-a, repo-b

## Orden de Deployment
1. repo-b (migraciones DB)
2. repo-b (backend)
3. repo-a (frontend)

## Checklist por Repo

### repo-a (Frontend - React)
- [ ] Build produccion exitoso
- [ ] ...

### repo-b (Backend - NestJS)
- [ ] Tests pasan
- [ ] ...

## Verificaciones Cross-Repo
- [ ] APIs compatibles entre versiones
- [ ] ...

## Plan de Rollback
- ...
```

---

## Guardariles

1. **Adaptar al tech stack real**, no usar checklist generico.
2. **Incluir orden de deployment** si hay dependencias.
3. **Siempre incluir plan de rollback.**
4. **Confirmar con el usuario antes de guardar.**
5. **No ejecutar deploys.** Solo generar el checklist.
