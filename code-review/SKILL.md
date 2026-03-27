---
name: code-review
description: Revision de codigo cross-repo enfocada en consistencia de APIs, tipos, integraciones y gaps de testing.
license: MIT
metadata:
  author: nbx-hub
  version: "1.0"
---

Revision de codigo transversal entre repositorios. Evaluas consistencia de APIs, contratos de datos, integraciones y cobertura de tests para un feature o epica.

---

## Postura

- **Constructivo**: Senala problemas con sugerencias concretas, nunca solo critica.
- **Sistemico**: Revisa la interaccion entre repos, no solo codigo aislado.
- **Basado en evidencia**: Cada observacion referencia archivos y lineas especificas.

---

## Entrada

- Epica, feature branch o lista de PRs a revisar.
- Repos involucrados (o detectar desde la epica).

---

## Pasos

### 1. Identificar alcance

Lee la epica o descripcion del feature. Determina repos afectados.

### 2. Revisar contratos entre repos

- APIs: endpoints, request/response schemas coinciden entre consumidor y proveedor.
- Tipos compartidos: interfaces, DTOs, enums son consistentes.
- Variables de entorno: las mismas keys usadas en ambos lados.

### 3. Revisar calidad por repo

Para cada repo afectado:
- Manejo de errores: casos edge cubiertos.
- Validaciones: inputs validados en los boundaries.
- Naming y convenciones: consistentes con el repo existente.
- Seguridad: sin secrets hardcoded, inyecciones, XSS.

### 4. Verificar cobertura de tests

- Tests unitarios cubren logica nueva.
- Tests de integracion cubren interaccion entre servicios.
- Mocks consistentes con la implementacion real.

### 5. Generar reporte

```markdown
# Code Review: <feature>

**Fecha**: YYYY-MM-DD
**Repos revisados**: repo-a, repo-b

## Resumen
<1-3 oraciones>

## Hallazgos Criticos
| # | Repo | Archivo | Linea | Problema | Sugerencia |
|---|------|---------|-------|----------|------------|

## Consistencia Cross-Repo
- [ ] Contratos API alineados
- [ ] Tipos compartidos consistentes
- [ ] Variables de entorno sincronizadas

## Cobertura de Tests
| Repo | Unit | Integration | Gaps |
|------|------|-------------|------|

## Recomendaciones
1. ...
```

---

## Guardariles

1. **No modificar codigo.** Solo revisar y reportar.
2. **Priorizar hallazgos criticos** sobre nitpicks de estilo.
3. **Siempre verificar cross-repo**, no solo repo individual.
4. **Fundamentar en codigo**: citar archivo:linea.
5. **Confirmar antes de guardar** el reporte.
