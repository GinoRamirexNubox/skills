---
name: epic-breakdown
description: Descomponer una epica existente en historias de usuario implementables con scope claro y asignaciones por repo.
license: MIT
metadata:
  author: nbx-hub
  version: "1.0"
---

Toma una epica existente y la descompone en historias implementables con scope claro, asignaciones por repositorio y grafo de dependencias.

---

## Entrada

Ruta a una epica existente o nombre del proyecto.

---

## Pasos

### 1. Leer la epica

Lee el documento de la epica. Si no se indica, preguntar al usuario.

### 2. Identificar repos

Identifica los repos disponibles en el workspace para entender el stack.

### 3. Analizar repos afectados

Para cada repo mencionado en la epica, leer codigo relevante para entender alcance real.

### 4. Descomponer en historias

Cada historia debe:
- Ser implementable de forma independiente.
- Tener < 8 story points.
- Tener criterios de aceptacion claros.
- Indicar repos afectados.
- Sugerir un `change-id` kebab-case para cada repo (ej: `agregar-endpoint-descuentos`).

### 5. Crear grafo de dependencias

```
HU-1 (sin deps)
  └─→ HU-2 (depende de HU-1)
  └─→ HU-3 (depende de HU-1)
HU-4 (paralelo con HU-2/HU-3)
```

### 6. Actualizar la epica

Agregar el desglose detallado al documento de la epica.

---

## Guardariles

- **Historias pequenas**: si una historia es > 8 pts, dividirla mas.
- **Dependencias explicitas**: cada dependencia debe ser justificada.
- **No implementar**: solo planificacion.
- **Pausar si hay ambiguedad**: preguntar antes de asumir.
