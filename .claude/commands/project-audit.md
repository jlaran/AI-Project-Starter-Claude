---
name: project-audit
description: Audit project health, organization, and documentation
tools:
  - bash
---

# Project Audit

Comprehensive audit of project health and organization.

## Step 1: Project Structure

```bash
find . -type d -not -path "*/node_modules/*" -not -path "*/.git/*" -not -path "*/dist/*" -not -path "*/build/*" | head -30
```

## Step 2: Documentation Check

```bash
ls -la README* CONTRIBUTING* CHANGELOG* LICENSE* 2>/dev/null || echo "Check documentation files"
```

```bash
cat README.md 2>/dev/null | head -50
```

## Step 3: Dependency Health

```bash
npm outdated 2>/dev/null || yarn outdated 2>/dev/null || echo "No package manager found"
```

```bash
npm audit --audit-level=moderate 2>/dev/null || echo "Skipping npm audit"
```

## Step 4: Code Hygiene

### Dead Code (unused exports)
```bash
grep -r "export " --include="*.{js,ts,tsx}" . 2>/dev/null | wc -l
```

### TODO/FIXME Comments
```bash
grep -rn "TODO\|FIXME\|HACK\|XXX" --include="*.{js,ts,tsx,py}" . 2>/dev/null | head -20
```

### Console Statements
```bash
grep -rn "console\.\(log\|debug\|info\)" --include="*.{js,ts,tsx}" . 2>/dev/null | grep -v "node_modules" | head -10
```

## Step 5: Test Coverage

```bash
ls -la tests/ test/ __tests__/ spec/ 2>/dev/null || echo "Check test directory structure"
```

```bash
find . -name "*.test.*" -o -name "*.spec.*" 2>/dev/null | grep -v node_modules | wc -l
```

## Step 6: Configuration Consistency

```bash
ls -la .env* tsconfig* .eslint* .prettier* 2>/dev/null
```

```bash
cat .env.example 2>/dev/null || echo "No .env.example found"
```

## Step 7: Generate Audit Report

```markdown
## Project Health Audit

### Summary
- Overall Health: [Good/Fair/Needs Attention]
- Documentation: [Complete/Partial/Missing]
- Dependencies: [Up-to-date/Outdated/Vulnerable]
- Code Hygiene: [Clean/Needs Cleanup]
- Test Coverage: [Good/Partial/Missing]

### Documentation
| File | Status |
|------|--------|
| README.md | ✓/✗ |
| CONTRIBUTING.md | ✓/✗ |
| CHANGELOG.md | ✓/✗ |
| LICENSE | ✓/✗ |

### Dependency Issues
[List of outdated/vulnerable dependencies]

### Code Hygiene Issues
- TODOs found: [count]
- Console logs: [count]
- Dead code areas: [list]

### Recommended Actions
1. [High priority action]
2. [Medium priority action]
3. [Low priority action]
```
