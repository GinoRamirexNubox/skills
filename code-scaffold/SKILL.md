---
name: code-scaffold
description: Scaffoldea la estructura de un feature cross-repo creando artefactos de cambio (proposal, tasks) en cada repositorio afectado.
license: MIT
metadata:
  author: nbx-hub
  version: "1.0"
---

Crea la estructura de planificacion para implementar un feature en uno o mas repos. **NO implementa codigo**. Solo genera artefactos de cambio (`proposal.md`, `tasks.md`, opcionalmente `design.md`) dentro de cada repo afectado.

---

## Entrada

- Historia de usuario (desde epica) o descripcion libre de feature.
- `change-id`: identificador kebab-case.
- `repos` (opcional): lista explicita de repos afectados.

---

## Pasos

### 1. Comprender el feature

Lee historia de usuario, discovery, o descripcion. Extrae objetivo, criterios y repos afectados.

### 2. Identificar repos afectados

Identifica los repos disponibles en el workspace. Verifica que cada ruta existe en disco.

### 3. Crear artefactos en cada repo

Para cada repo afectado, crea:

```
<repo-path>/openspec/changes/<change-id>/
  proposal.md   -- Objetivo, alcance, criterios para ESTE repo
  tasks.md      -- Tareas ordenadas con dependencias
  design.md     -- (opcional) Si es multi-sistema o arquitectonico
```

### 4. Reportar resumen

```
## Resumen de Scaffold

| Repositorio | Ruta | Artefactos |
|------------|------|-----------|
| repo-a | .../openspec/changes/<id>/ | proposal.md, tasks.md |
```

---

## Guardariles

1. **Nunca escribir codigo de aplicacion.** Solo artefactos markdown.
2. **Verificar que las rutas existen** antes de crear directorios.
3. **Propuestas enfocadas**: cada `proposal.md` es especifico para ESE repo.
4. **No sobrescribir**: si el change-id ya existe, preguntar.
5. **Usar kebab-case** para change-id.
