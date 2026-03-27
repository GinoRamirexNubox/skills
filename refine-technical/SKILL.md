---
name: refine-technical
description: Toma un artefacto de descubrimiento o requerimiento bruto y produce una especificacion tecnica refinada por repositorio.
license: MIT
metadata:
  author: nbx-hub
  version: "1.0"
---

Recibe un artefacto de descubrimiento, epica o requerimiento en bruto y genera una especificacion tecnica detallada, anclada en el codigo real de cada repositorio afectado.

---

## Entrada

- Ruta a un documento de descubrimiento, nombre de epica, o descripcion libre.
- Si no se indica, preguntar antes de continuar.

---

## Pasos

### 1. Identificar repos disponibles

Identifica los repos en el workspace actual. Busca registros de repos, monorepo configs, o pregunta al usuario.

### 2. Comprender el artefacto de entrada

Lee el documento, identifica objetivos funcionales y restricciones.

### 3. Identificar repositorios afectados

Cruza capacidades con repos disponibles. Confirma leyendo estructura y archivos clave.

### 4. Analizar cada repositorio afectado

Para cada repo:
1. **APIs existentes** — endpoints, controladores, contratos.
2. **Modelos de datos** — schemas, entidades, tipos.
3. **Puntos de integracion** — llamadas entre servicios, eventos.
4. **Dependencias internas** — otros repos del workspace afectados.

### 5. Evaluar riesgos tecnicos

Areas de alta complejidad, poca cobertura, dependencias fragiles. Marcar supuestos como "SUPUESTO - requiere validacion".

### 6. Estimar complejidad por repositorio

| Nivel | Significado |
|-------|-------------|
| Baja  | Cambio aislado, pocos archivos |
| Media | Varios archivos, posible migracion |
| Alta  | Multiples servicios, migraciones complejas |

---

## Formato de salida

```markdown
# Refinamiento Tecnico: <titulo>

## Resumen
## Repositorios afectados
### <nombre-repo>
- Ruta, Complejidad, Cambios de API, Modelos, Integraciones, Archivos clave
## Dependencias entre repositorios
## Riesgos tecnicos
| # | Riesgo | Repo | Severidad | Mitigacion |
## Supuestos y preguntas abiertas
## Siguiente paso sugerido
```

---

## Guardariles

- **Anclar en codigo real**: toda afirmacion respaldada por archivos concretos.
- **Marcar lo desconocido** explicitamente.
- **No modificar archivos fuente**: solo lee y documenta.
