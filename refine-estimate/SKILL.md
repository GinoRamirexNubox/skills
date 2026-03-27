---
name: refine-estimate
description: Estima complejidad y esfuerzo de historias de usuario usando story points fibonacci con justificacion basada en codigo.
license: MIT
metadata:
  author: nbx-hub
  version: "1.0"
---

Estima la complejidad de historias de usuario usando escala fibonacci (1, 2, 3, 5, 8, 13), analizando el codigo real de los repos afectados para justificar cada estimacion.

---

## Entrada

- Historias de usuario (desde una epica o proporcionadas directamente).
- Si no se proporcionan, preguntar al usuario.

---

## Pasos

### 1. Leer las historias

Lee las historias desde la epica del proyecto o del input del usuario.

### 2. Analizar codebase por historia

Para cada historia, lee el codigo de los repos afectados y evalua:
- Numero de archivos a modificar.
- Complejidad cross-repo (APIs, tipos compartidos).
- Necesidad de tests nuevos.
- Riesgo de regresion.
- Migraciones o cambios de esquema.

### 3. Estimar con justificacion

| Puntos | Significado |
|--------|-------------|
| 1 | Cambio trivial, un archivo, sin riesgo |
| 2 | Cambio simple, pocos archivos, bajo riesgo |
| 3 | Cambio moderado, varios archivos, un repo |
| 5 | Cambio significativo, cross-repo o con migracion |
| 8 | Cambio complejo, multiples repos, alto riesgo |
| 13 | Muy complejo, considerar dividir la historia |

### 4. Senalar historias grandes

Historias > 8 puntos deben ser senaladas con sugerencia de como dividirlas.

---

## Formato de salida

```markdown
# Estimacion: <nombre de epica o contexto>

| # | Historia | Puntos | Justificacion | Sugerencia |
|---|----------|--------|---------------|------------|
| 1 | HU-1: ... | 3 | 4 archivos en repo-web, sin migracion | - |
| 2 | HU-2: ... | 8 | Cross-repo, nueva API + frontend | Dividir en API y UI |

**Total**: N puntos
**Historias que sugiero dividir**: HU-2 (8 pts)
```

---

## Guardariles

- **Justificar con codigo**: cada estimacion referencia archivos reales.
- **No inventar**: si no puedes analizar un repo, marcarlo como incertidumbre.
- **Senalar historias grandes** (> 8 puntos) siempre.
