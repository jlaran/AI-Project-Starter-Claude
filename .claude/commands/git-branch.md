---
name: git-branch
description: Create a properly named feature branch from the current context
tools:
  - bash
---

# Branch Creator

Create a well-named branch following team conventions.

## Step 1: Check Current State

```bash
git status
```

```bash
git branch --show-current
```

## Step 2: Update Base Branch

```bash
git fetch origin
```

## Step 3: Determine Branch Name

Based on the work context, create a branch name following:

```
<type>/<ticket-id>-<short-description>
```

### Branch Types
| Prefix | Purpose |
|--------|---------|
| `feat/` | New features |
| `fix/` | Bug fixes |
| `hotfix/` | Urgent production fixes |
| `chore/` | Maintenance, dependencies |
| `docs/` | Documentation |
| `refactor/` | Code restructuring |
| `test/` | Test additions/fixes |

### Naming Rules
- Use lowercase
- Use hyphens (not underscores)
- Keep it short but descriptive
- Include ticket ID if available

### Examples
- `feat/PROJ-123-user-authentication`
- `fix/login-button-disabled`
- `chore/upgrade-typescript`

## Step 4: Create Branch

```bash
git checkout -b <branch-name>
```

## Step 5: Verify

```bash
git branch --show-current
```

```bash
git log --oneline -1
```
