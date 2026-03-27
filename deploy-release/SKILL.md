---
name: deploy-release
description: Gestion de release multi-repo - coordinar versionado, archivar cambios y actualizar changelogs.
license: MIT
metadata:
  author: nbx-hub
  version: "1.0"
---

Coordina el proceso de release a traves de multiples repositorios. Gestiona versionado, archiva artefactos de cambio completados y actualiza changelogs.

---

## Entrada

- Version de la release (semver: major.minor.patch).
- Epica o features incluidos.
- Repos involucrados.

---

## Pasos

### 1. Inventariar cambios incluidos

Lee las epicas y features que forman parte de esta release. Para cada repo, identifica:
- Cambios completados.
- PRs mergeados.
- Funcionalidad nueva, fixes, breaking changes.

### 2. Clasificar cambios por tipo

Segun Keep a Changelog:
- **Agregado**: Funcionalidad nueva.
- **Cambiado**: Cambios en funcionalidad existente.
- **Obsoleto**: Features que seran removidos.
- **Removido**: Features eliminados.
- **Arreglado**: Bug fixes.
- **Seguridad**: Fixes de vulnerabilidades.

### 3. Actualizar changelogs

Actualizar el changelog del proyecto con vista unificada.

### 4. Generar nota de release

```markdown
# Release v<version>

**Fecha**: YYYY-MM-DD

## Repos Incluidos
| Repo | Version Anterior | Version Nueva |
|------|-----------------|---------------|

## Cambios

### Agregado
- ...

### Arreglado
- ...

## Notas de Migracion
- ...

## Problemas Conocidos
- ...
```

---

## Guardariles

1. **Confirmar cada archivo antes de mover/archivar.**
2. **No ejecutar git tag ni push.** Solo preparar artefactos.
3. **Respetar semver**: breaking changes = major, features = minor, fixes = patch.
4. **Verificar que el checklist pre-deploy esta completo** antes de proceder.
5. **No borrar artefactos**, solo archivar.
