---
name: sprint-plan
description: Crear un plan de sprint seleccionando historias de epicas, verificando capacidad y organizando el backlog.
license: MIT
metadata:
  author: nbx-hub
  version: "1.0"
---

Crea un plan de sprint seleccionando historias de epicas activas, verificando capacidad y dependencias.

---

## Entrada

- Numero o nombre del sprint.
- Capacidad disponible (story points).
- Epica(s) de origen.

---

## Pasos

### 1. Listar historias disponibles

Lee las epicas activas y lista las historias pendientes con sus puntos estimados.

### 2. Priorizar dentro de capacidad

Ayuda al usuario a seleccionar historias respetando la capacidad. Sugiere dejar 10% de margen.

### 3. Verificar dependencias

Verifica que las historias seleccionadas respetan el orden de dependencias.

### 4. Generar sprint backlog

```markdown
# Sprint <N>

**Fecha**: YYYY-MM-DD
**Capacidad**: <N> puntos
**Objetivo del sprint**: <objetivo>

## Historias Seleccionadas

| # | Historia | Puntos | Repo(s) | Dependencia |
|---|----------|--------|---------|-------------|
| 1 | HU-X     | 3      | repo-a  | ninguna     |

**Total comprometido**: <N> puntos
**Margen**: <N> puntos

## Orden de ejecucion sugerido
1. HU-X (sin deps)
2. HU-Y (depende de HU-X)

## Riesgos del sprint
- ...
```

---

## Guardariles

- **Respetar capacidad**: nunca comprometer mas puntos de los disponibles.
- **Verificar dependencias**: no incluir historias con deps no resueltas.
- **Confirmar antes de guardar**.
