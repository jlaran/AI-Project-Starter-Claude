---
name: create-pr
description: Create a well-documented pull request from the current branch
tools:
  - bash
---

# Pull Request Creator

Create a comprehensive pull request with proper documentation.

## Step 1: Verify Branch State

```bash
git status
```

```bash
git branch --show-current
```

## Step 2: Check Commits to Include

```bash
git log --oneline main..HEAD
```

## Step 3: View Changes Summary

```bash
git diff main --stat
```

## Step 4: Analyze Changes

```bash
git diff main
```

## Step 5: Push Branch

```bash
git push -u origin HEAD
```

## Step 6: Create Pull Request

Based on the commits and changes, create a PR with:

### Title Format
```
<type>(<scope>): <description>
```

### Body Template
```markdown
## Summary
[1-2 sentence description of what this PR does]

## Changes
- [Change 1]
- [Change 2]
- [Change 3]

## Testing
- [ ] Unit tests added/updated
- [ ] Manual testing completed
- [ ] Edge cases considered

## Screenshots
[If UI changes, add screenshots]

## Related Issues
Closes #[issue-number]
```

Execute with GitHub CLI:

```bash
gh pr create --title "<title>" --body "<body>"
```

## Step 7: Verify PR Created

```bash
gh pr view
```
