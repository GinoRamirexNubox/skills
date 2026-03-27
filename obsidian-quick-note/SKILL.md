---
name: obsidian-quick-note
description: Captura rápida de notas al Inbox del vault Obsidian. Cada entrada se tagea con fecha y hora para proceso posterior. Uso - /obsidian-quick-note <nota rápida>
---

# Inbox — Captura rápida

Captura notas rápidas en el archivo `Extra/Inbox.md` del vault, con timestamp para proceso posterior.

## Cómo funciona

1. Recibe el texto del usuario como argumento (todo lo que viene después de `/obsidian-quick-note`)
2. Genera un timestamp con formato `YYYY-MM-DD HH:mm`
3. Hace append al archivo `Extra/Inbox.md` usando Obsidian CLI
4. Confirma la captura con un mensaje breve

## Comando

```bash
obsidian append path="Extra/Inbox.md" content="- **{{timestamp}}** — {{nota}}" silent
```

Donde:
- `{{timestamp}}` = fecha y hora actual en formato `YYYY-MM-DD HH:mm` (usar `date +"%Y-%m-%d %H:%M"` para obtenerlo)
- `{{nota}}` = el texto que el usuario escribió después de `/obsidian-quick-note`

## Reglas

- Si el archivo `Extra/Inbox.md` no existe, crearlo primero con el frontmatter y encabezado base (ver abajo)
- Cada entrada es un bullet point (`-`) con el timestamp en bold y la nota después de un guion largo (`—`)
- NO abrir el archivo en Obsidian (usar `silent`)
- Responder solo con una confirmación corta, sin verbosidad
- Si el usuario no pasa texto, preguntar qué quiere capturar

## Formato del archivo Inbox (si no existe)

```markdown
---
tags:
  - nav/inbox
cssclasses:
  - inbox
---

# Inbox

> [!info] Notas pendientes de procesar
> Revisa este archivo periódicamente y mueve cada nota a su lugar en el vault.

---

```

## Ejemplo

Usuario: `/inbox revisar el artículo de James Clear sobre hábitos compuestos`

Resultado en `Extra/Inbox.md`:
```markdown
- **2026-03-25 14:32** — Revisar el artículo de James Clear sobre hábitos compuestos
```

Respuesta: `Capturado en Inbox.`
