---
name: epic-create
description: Crear una nueva epica con objetivos, criterios de aceptacion y desglose inicial de historias de usuario.
license: MIT
metadata:
  author: nbx-hub
  version: "1.0"
---

Crea una nueva epica con objetivo, contexto, criterios de aceptacion y un desglose inicial de historias de usuario.

---

## Entrada

Nombre o descripcion de la epica. Si no se proporciona, preguntar al usuario.

---

## Pasos

### 1. Obtener y validar la descripcion

Si el usuario no incluye descripcion clara, preguntar. Si es ambigua, clarificar.

### 2. Derivar nombre en kebab-case

Generar identificador (ej: `gestion-inventario`). Mostrar al usuario y esperar confirmacion.

### 3. Redactar la epica

Completar cada seccion:
- **Objetivo**: 1-2 oraciones.
- **Contexto**: situacion actual, motivacion.
- **Criterios de Aceptacion**: condiciones verificables.
- **Historias de Usuario**: formato `Como <rol>, quiero <accion>, para <beneficio>`. 3-8 historias iniciales.
- **Repos Afectados**: identificar repos del workspace involucrados.
- **Dependencias**, **Riesgos**, **Preguntas Abiertas**.

### 4. Referenciar artefactos de descubrimiento

Buscar documentos de discovery o entrevistas previas relacionados. Si existen, agregar seccion Referencias.

### 5. Pausar para revision

Mostrar borrador al usuario. No guardar hasta confirmacion explicita.

### 6. Guardar

Escribir la epica en la ubicacion que el usuario indique, con frontmatter:

```yaml
---
artifact-id: <nombre>-epic
version: 1.0.0
date: YYYY-MM-DD
author: architect-agent
status: active
---
```

---

## Guardariles

- **No avanzar sin comprension clara**: detenerse y preguntar ante vaguedad.
- **Pausar antes de guardar**: siempre esperar aprobacion.
- **No implementar codigo**: solo documentacion de planificacion.
- **Nombres unicos**: verificar que no exista una epica con el mismo nombre.
