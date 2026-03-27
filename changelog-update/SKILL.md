---
name: changelog-update
description: Actualizar el changelog unificado del producto siguiendo el formato Keep a Changelog en espanol.
license: MIT
metadata:
  author: nbx-hub
  version: "1.0"
---

Actualiza el changelog del proyecto siguiendo el formato Keep a Changelog. Recopila cambios de los repos involucrados y los presenta de forma coherente.

---

## Entrada

- Version o rango de fechas a documentar.
- Repos involucrados (opcional, por defecto todos los del workspace).

---

## Pasos

### 1. Recopilar cambios

Para cada repo en el workspace:
- Revisa commits recientes o PRs mergeados.
- Busca artefactos de cambio si existen.
- Identifica mejoras al workspace (nuevos skills, cambios de estructura, mejoras de proceso).

### 2. Clasificar segun Keep a Changelog

Categorias (en espanol):
- **Agregado**: Funcionalidad nueva.
- **Cambiado**: Cambios en funcionalidad existente.
- **Obsoleto**: Features que seran removidos pronto.
- **Removido**: Features eliminados.
- **Arreglado**: Correccion de bugs.
- **Seguridad**: Parches de vulnerabilidades.

### 3. Redactar entradas

Cada entrada debe:
- Describir el cambio desde perspectiva de usuario/producto, no tecnica.
- Indicar repo(s) afectado(s) entre parentesis si es relevante.
- Ser concisa: 1 linea por cambio.

### 4. Actualizar archivo

Lee el CHANGELOG.md existente y agrega la nueva seccion:

```markdown
## [X.Y.Z] - YYYY-MM-DD

### Agregado
- Descripcion del cambio (repo-a, repo-b)

### Arreglado
- Descripcion del fix (repo-c)
```

---

## Guardariles

1. **Formato Keep a Changelog estricto.** No inventar categorias.
2. **Perspectiva de producto**, no tecnica. "Agregado soporte para X" no "Agregado endpoint POST /api/x".
3. **No perder contenido existente** del changelog.
4. **Confirmar con el usuario antes de guardar.**
5. **Fechas en formato ISO** (YYYY-MM-DD).
