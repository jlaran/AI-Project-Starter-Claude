# Git Workflow Skill

Professional git practices and workflows.

## Commit Message Format

```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

### Types
- `feat` - New feature
- `fix` - Bug fix
- `docs` - Documentation
- `style` - Formatting
- `refactor` - Code restructure
- `perf` - Performance
- `test` - Tests
- `chore` - Maintenance

### Examples
```
feat(auth): add OAuth2 support

Implement Google and GitHub providers.
Token refresh handled automatically.

Closes #123
```

## Branch Naming

```
<type>/<ticket>-<description>
```

Examples:
- `feat/PROJ-123-user-auth`
- `fix/PROJ-456-cart-total`
- `chore/upgrade-deps`

## Common Operations

### Start New Feature
```bash
git checkout main
git pull origin main
git checkout -b feat/description
```

### Commit Changes
```bash
git add <files>
git commit -m "type(scope): description"
```

### Update Branch
```bash
git fetch origin
git rebase origin/main
```

### Clean Up History
```bash
git rebase -i HEAD~5
# squash/fixup commits
```

### Undo Last Commit
```bash
# Keep changes staged
git reset --soft HEAD~1

# Discard changes
git reset --hard HEAD~1
```

### Stash Work
```bash
git stash push -m "WIP: description"
git stash pop
```

## Pull Request Checklist

- [ ] Branch is up to date with main
- [ ] Tests pass
- [ ] Code reviewed (self)
- [ ] Commit history is clean
- [ ] PR description is complete

## PR Description Template

```markdown
## Summary
What this PR does.

## Changes
- Change 1
- Change 2

## Testing
- [ ] Unit tests
- [ ] Manual testing

## Related Issues
Closes #123
```

## Merge Strategies

| Strategy | When to Use |
|----------|-------------|
| Merge commit | Preserve full history |
| Squash | Messy branch history |
| Rebase | Linear history preferred |
