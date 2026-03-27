---
name: test-e2e-plan
description: Crear plan de pruebas end-to-end a partir de epicas y especificaciones tecnicas.
license: MIT
metadata:
  author: nbx-hub
  version: "1.0"
---

Genera un plan de pruebas end-to-end que cubra flujos completos de usuario a traves de multiples repositorios. Parte de la epica y especificaciones tecnicas para definir escenarios, datos de prueba y criterios de exito.

---

## Entrada

- Epica o especificacion tecnica del feature.
- Repos involucrados (opcional).

---

## Pasos

### 1. Leer epica y criterios de aceptacion

Extrae los criterios de aceptacion de la epica. Cada criterio se convierte en al menos un escenario E2E.

### 2. Mapear flujos de usuario

Identifica los flujos completos que atraviesan repos:
- Flujo feliz (happy path).
- Flujos alternativos.
- Flujos de error.

### 3. Identificar puntos de integracion

Lee el codigo relevante para mapear:
- Frontend → BFF/API.
- BFF → Servicios backend.
- Servicios → Base de datos / Servicios externos.

### 4. Definir escenarios de prueba

Para cada flujo:
- **Precondiciones**: estado inicial requerido.
- **Pasos**: acciones del usuario o sistema.
- **Resultado esperado**: que debe ocurrir.
- **Datos de prueba**: datos necesarios.

### 5. Generar plan

```markdown
# Plan de Pruebas E2E: <epica>

**Fecha**: YYYY-MM-DD
**Repos involucrados**: repo-a, repo-b

## Flujos Identificados

### Flujo 1: <nombre>
**Tipo**: Happy path / Alternativo / Error
**Repos**: repo-a → repo-b

| Paso | Accion | Resultado Esperado |
|------|--------|--------------------|
| 1    | ...    | ...                |

**Precondiciones**: ...
**Datos de prueba**: ...

## Matriz de Cobertura

| Criterio de Aceptacion | Escenario(s) | Estado |
|------------------------|--------------|--------|
| CA-1                   | Flujo 1, 3   | Pendiente |

## Riesgos de Testing
- ...

## Dependencias
- ...
```

---

## Guardariles

1. **Cada criterio de aceptacion debe tener al menos un escenario.**
2. **No escribir codigo de tests.** Solo el plan.
3. **Incluir flujos de error**, no solo happy paths.
4. **Confirmar con el usuario antes de guardar.**
5. **Referenciar archivos concretos** donde se implementan los endpoints/componentes.
