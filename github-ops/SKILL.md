---
name: github-ops
description: Operaciones de GitHub CLI (gh) para interactuar con repos, PRs, issues y releases.
license: MIT
metadata:
  author: nbx-hub
  version: "1.0"
---

Encapsula operaciones de GitHub CLI (`gh`) para interactuar con repositorios, pull requests, issues, branches y releases de forma estandarizada y segura.

---

## Prerrequisitos

- `gh` CLI instalado y autenticado (`gh auth status`).

---

## Postura

- **Estandarizado**: Todas las operaciones pasan por `gh` CLI, nunca por API directa.
- **Seguro por capas**: Lectura libre, escritura con confirmacion, merge con doble confirmacion.

---

## Resolucion de Repos

Cuando una operacion recibe un nombre de repo:

1. **Nombre corto** (ej: `mi-repo`): Si existe un registro de repos en el workspace, busca ahi. Si no, pregunta al usuario la org (o usa la del repo actual).
2. **Nombre completo** (ej: `org/mi-repo`): Usa directamente.

---

## Operaciones

### Repositorios

#### Listar repos de la org `[LECTURA]`

```bash
gh repo list <org> --limit <n> --json name,description,language,pushedAt,isArchived
```

#### Ver info de un repo `[LECTURA]`

```bash
gh repo view <org>/<repo> --json name,description,url,defaultBranchRef,languages,pushedAt,createdAt,isPrivate,isArchived
```

#### Clonar repo `[ESCRITURA - CONFIRMACION]`

```bash
gh repo clone <org>/<repo>
```

---

### Pull Requests

#### Listar PRs `[LECTURA]`

```bash
gh pr list -R <org>/<repo> --state <open|closed|merged|all> --json number,title,state,author,createdAt,updatedAt
```

#### Ver detalle de PR `[LECTURA]`

```bash
gh pr view <numero> -R <org>/<repo> --json number,title,body,state,author,baseRefName,headRefName,files,reviews,comments
```

Para ver diff:
```bash
gh pr diff <numero> -R <org>/<repo>
```

#### Crear PR `[ESCRITURA - CONFIRMACION]`

```bash
gh pr create --title "<titulo>" --body "<descripcion>" --base <branch-base> --head <branch-head>
```

Antes de crear, mostrar al usuario: titulo, descripcion, branch base y head, y pedir confirmacion.

#### Merge PR `[ESCRITURA - DOBLE CONFIRMACION]`

```bash
gh pr merge <numero> -R <org>/<repo> --merge|--squash|--rebase
```

**Doble confirmacion**:
1. Mostrar detalle del PR (titulo, branch, reviews, checks).
2. Preguntar: "Confirmas el merge del PR #X en <branch-base>?"
3. Preguntar: "Esta accion es irreversible. Proceder con merge?"

---

### Issues

#### Listar issues `[LECTURA]`

```bash
gh issue list -R <org>/<repo> --state <open|closed|all> --json number,title,state,author,labels,createdAt
```

#### Ver detalle de issue `[LECTURA]`

```bash
gh issue view <numero> -R <org>/<repo> --json number,title,body,state,author,labels,comments,assignees
```

#### Crear issue `[ESCRITURA - CONFIRMACION]`

```bash
gh issue create -R <org>/<repo> --title "<titulo>" --body "<descripcion>" --label "<labels>"
```

#### Comentar issue `[ESCRITURA - CONFIRMACION]`

```bash
gh issue comment <numero> -R <org>/<repo> --body "<comentario>"
```

---

### Branches y Releases

#### Listar branches remotos `[LECTURA]`

```bash
gh api repos/<org>/<repo>/branches --jq '.[].name'
```

#### Listar releases/tags `[LECTURA]`

```bash
gh release list -R <org>/<repo> --json tagName,name,publishedAt,isPrerelease,isDraft
```

---

## Formato de Salida

Presentar resultados en tablas markdown cuando sea posible:

```markdown
| # | Titulo | Estado | Autor | Fecha |
|---|--------|--------|-------|-------|
| 14 | Fix login timeout | open | usuario | 2025-12-01 |
```

---

## Guardariles

1. **Verificar autenticacion** al inicio: ejecutar `gh auth status` si hay duda.
2. **Operaciones de lectura se ejecutan directamente**, sin pedir confirmacion.
3. **Operaciones de escritura requieren confirmacion** del usuario antes de ejecutar.
4. **Merge de PR requiere doble confirmacion** explicita.
5. **Nunca ejecutar** `gh repo delete`, `gh issue close`, `gh pr close` sin autorizacion explicita del usuario.
6. **Manejar errores**: si `gh` falla, reportar el error claramente sin reintentar automaticamente.
7. **No cachear ni asumir estado**: cada operacion consulta el estado actual de GitHub.
