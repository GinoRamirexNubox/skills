---
name: adr-create
description: Crear Architecture Decision Records para documentar decisiones tecnicas importantes del ecosistema.
license: MIT
metadata:
  author: nbx-hub
  version: "1.0"
---

Crea un Architecture Decision Record (ADR) para documentar decisiones tecnicas significativas. Sigue el formato estandar ADR y numera secuencialmente.

---

## Entrada

- Topico de la decision o pregunta tecnica.
- Contexto adicional (opcional).

---

## Pasos

### 1. Entender la decision

Pregunta al usuario:
- Cual es la decision o pregunta tecnica?
- Que alternativas se consideraron?
- Que restricciones existen?
- Que repos o sistemas afecta?

Si la decision no es clara, clarificar antes de continuar.

### 2. Investigar contexto

Lee codigo relevante del workspace para fundamentar la decision con evidencia del codebase actual.

Revisa ADRs existentes en el proyecto para evitar contradecir decisiones previas vigentes.

### 3. Determinar numero secuencial

Lista ADRs existentes. El nuevo ADR sera `NNNN-<titulo-kebab>.md` donde NNNN es el siguiente numero disponible (ej: `0001-`, `0002-`).

### 4. Redactar ADR

```yaml
---
artifact-id: adr-NNNN
version: 1.0.0
date: YYYY-MM-DD
author: architect-agent
status: active
adr-status: Propuesto | Aceptado | Deprecado | Reemplazado por ADR-XXXX
---
```

- **Titulo**: Descriptivo, en espanol.
- **Contexto**: Situacion que motiva la decision. Incluir evidencia del codebase.
- **Decision**: Que se decidio y por que.
- **Alternativas Consideradas**: Otras opciones con pros/contras.
- **Consecuencias**: Impacto positivo y negativo de la decision.

### 5. Pausar para revision

Mostrar borrador al usuario. No guardar hasta confirmacion explicita.

### 6. Guardar

Escribir en la ubicacion que el usuario indique.

---

## Guardariles

1. **Nunca guardar sin confirmacion del usuario.**
2. **Fundamentar en el codebase**: el contexto debe referenciar codigo real.
3. **Incluir siempre alternativas**, aunque parezcan inferiores.
4. **Numerar secuencialmente**, sin gaps.
5. **No modificar ADRs aceptados**. Si cambia la decision, crear uno nuevo que reemplace al anterior.
