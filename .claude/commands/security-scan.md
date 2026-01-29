---
name: security-scan
description: Scan code for security vulnerabilities
tools:
  - bash
---

# Security Scanner

Scan the codebase for common security vulnerabilities.

## Step 1: Check Dependencies

```bash
npm audit 2>/dev/null || yarn audit 2>/dev/null || echo "No npm/yarn found"
```

## Step 2: Look for Hardcoded Secrets

Search for potential secrets in code:

```bash
grep -r --include="*.{js,ts,jsx,tsx,py,go,java}" -E "(api[_-]?key|secret|password|token|credential).*[=:].*['\"][^'\"]{8,}['\"]" . 2>/dev/null | head -20
```

## Step 3: Check for Dangerous Patterns

### SQL Injection Patterns
```bash
grep -r --include="*.{js,ts,py}" -E "(query|execute|exec)\s*\([^)]*\+|`[^`]*\$\{" . 2>/dev/null | head -10
```

### Command Injection Patterns
```bash
grep -r --include="*.{js,ts,py}" -E "(exec|spawn|system|eval)\s*\(" . 2>/dev/null | head -10
```

## Step 4: Review Environment Files

```bash
find . -name ".env*" -o -name "*.env" 2>/dev/null
```

```bash
cat .gitignore 2>/dev/null | grep -E "\.env|secret|credential" || echo "Check .gitignore for env files"
```

## Step 5: Check Security Headers (if applicable)

Look for security header configuration in the codebase.

## Step 6: Generate Report

Based on findings, create a security report:

```markdown
## Security Scan Report

### Summary
- Critical: [count]
- High: [count]
- Medium: [count]
- Low: [count]

### Findings

#### [Finding Title]
- **Severity**: Critical/High/Medium/Low
- **Location**: [file:line]
- **Description**: [what the issue is]
- **Impact**: [what could happen]
- **Recommendation**: [how to fix]

### Recommendations
1. [Priority action 1]
2. [Priority action 2]
```

## OWASP Top 10 Quick Check

- [ ] A01: Broken Access Control
- [ ] A02: Cryptographic Failures
- [ ] A03: Injection
- [ ] A04: Insecure Design
- [ ] A05: Security Misconfiguration
- [ ] A06: Vulnerable Components
- [ ] A07: Auth Failures
- [ ] A08: Data Integrity Failures
- [ ] A09: Logging Failures
- [ ] A10: Server-Side Request Forgery
