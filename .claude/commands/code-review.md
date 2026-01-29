---
name: code-review
description: Perform a thorough code review of specified files or changes
tools:
  - bash
---

# Code Review

Perform a comprehensive code review of the specified code.

## Step 1: Identify Changes to Review

If reviewing PR changes:
```bash
git diff main --name-only
```

If reviewing specific files, read those files directly.

## Step 2: Get the Code

```bash
git diff main
```

## Step 3: Analyze Code

Review the code against these criteria:

### Correctness
- Does the code do what it's supposed to do?
- Are edge cases handled?
- Is error handling appropriate?

### Security
- Input validation present?
- No SQL injection, XSS, or other vulnerabilities?
- Sensitive data handled properly?

### Code Quality
- Single Responsibility Principle followed?
- No unnecessary duplication?
- Meaningful variable/function names?
- Functions reasonably sized?

### Testing
- Are there tests for new functionality?
- Do tests cover edge cases?

### Documentation
- Complex logic explained?
- Public APIs documented?

## Step 4: Generate Review

Output format:

```markdown
## Code Review

### Summary
[Brief overview of the changes]

### Critical Issues
[Must-fix security or correctness issues]

### Suggestions
[Improvements for code quality]

### Positive Observations
[Good patterns worth noting]

### Verdict
- [ ] Approved
- [ ] Approved with minor changes
- [ ] Changes requested
```

## Step 5: Provide Constructive Feedback

For each issue, include:
1. **What**: The specific problem
2. **Why**: Why it's a problem
3. **How**: Suggested fix or approach
