---
name: semantic-commit
description: Analyze staged changes and create a semantic commit message
tools:
  - bash
---

# Semantic Commit Generator

Analyze staged changes and create a properly formatted conventional commit.

## Step 1: Check Staged Changes

```bash
git status --short
```

```bash
git diff --staged --stat
```

## Step 2: Analyze Changes in Detail

```bash
git diff --staged
```

## Step 3: Generate Commit Message

Based on the staged changes, create a semantic commit following this format:

```
<type>(<scope>): <description>

[optional body with details]
```

### Commit Types
- **feat**: New feature
- **fix**: Bug fix
- **docs**: Documentation only
- **style**: Formatting, no code change
- **refactor**: Code change, no new feature or fix
- **perf**: Performance improvement
- **test**: Adding/correcting tests
- **chore**: Build, tooling, dependencies
- **ci**: CI/CD changes

### Guidelines
- Use imperative mood ("add" not "added")
- Keep first line under 72 characters
- Scope should be the component/module affected
- Body explains *why*, not *what* (the diff shows what)

## Step 4: Execute Commit

After analyzing changes, execute:

```bash
git commit -m "<generated message>"
```

## Step 5: Verify

```bash
git log --oneline -1
```
