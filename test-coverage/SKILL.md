---
name: test-coverage
description: Analisis de cobertura cross-repo - mapea requerimientos vs tests existentes e identifica gaps.
license: MIT
metadata:
  author: nbx-hub
  version: "1.0"
---

Analiza la cobertura de tests existente en relacion a los requerimientos de un feature o epica. Identifica gaps y genera una matriz de trazabilidad requerimiento-a-test.

---

## Entrada

- Feature, epica o lista de repos a analizar.
- Scope: puede ser un feature especifico o cobertura general.

---

## Pasos

### 1. Identificar requerimientos

Lee la epica o feature para extraer los requerimientos funcionales y criterios de aceptacion.

### 2. Inventariar tests existentes

Para cada repo afectado:
- Localiza directorios de tests (`__tests__/`, `test/`, `*.spec.*`, `*.test.*`).
- Clasifica: unitarios, integracion, e2e.
- Identifica que funcionalidad cubren.

### 3. Construir matriz de trazabilidad

Cruza requerimientos con tests existentes:

```
| Requerimiento | Test(s) | Tipo | Repo | Cobertura |
|--------------|---------|------|------|-----------|
| REQ-1        | auth.spec.ts:45 | Unit | repo-a | Parcial |
| REQ-2        | - | - | - | Sin cobertura |
```

### 4. Identificar gaps

- Requerimientos sin ningun test.
- Requerimientos con solo tests unitarios (falta integracion).
- Mocks desactualizados respecto a la implementacion real.
- Caminos de error no testeados.

### 5. Generar reporte

```markdown
# Analisis de Cobertura: <feature/epica>

**Fecha**: YYYY-MM-DD

## Resumen
- Requerimientos totales: N
- Con cobertura completa: N
- Con cobertura parcial: N
- Sin cobertura: N

## Matriz de Trazabilidad
| Requerimiento | Tests | Tipo | Repo | Estado |
|...

## Gaps Criticos
1. ...

## Recomendaciones
1. ...
```

---

## Guardariles

1. **Solo analizar, no escribir tests.**
2. **Buscar en el codebase real**, no asumir que existen tests.
3. **Diferenciar tipos de tests** (unit, integration, e2e).
4. **Priorizar gaps criticos** sobre cobertura de casos edge.
5. **Confirmar antes de guardar** el reporte.
