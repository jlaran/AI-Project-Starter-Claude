# Security Skill

Security best practices for application development.

## OWASP Top 10 Quick Reference

### 1. Injection
- Use parameterized queries
- Validate and sanitize input
- Escape output

### 2. Broken Authentication
- Strong password policies
- MFA when possible
- Secure session management

### 3. Sensitive Data Exposure
- Encrypt at rest and in transit
- Don't log sensitive data
- Proper key management

### 4. XXE (XML External Entities)
- Disable external entity processing
- Use JSON instead of XML

### 5. Broken Access Control
- Deny by default
- Check authorization on every request
- CORS properly configured

### 6. Security Misconfiguration
- Security headers set
- Error messages sanitized
- Unused features disabled

### 7. XSS
- Output encoding
- Content Security Policy
- HttpOnly cookies

### 8. Insecure Deserialization
- Avoid deserializing untrusted data
- Integrity checks

### 9. Vulnerable Components
- Regular dependency audits
- Keep dependencies updated

### 10. Insufficient Logging
- Log security events
- Protect logs from tampering

## Security Headers

```
Content-Security-Policy: default-src 'self'
X-Content-Type-Options: nosniff
X-Frame-Options: DENY
Strict-Transport-Security: max-age=31536000
X-XSS-Protection: 1; mode=block
```

## Input Validation

```typescript
// Allowlist preferred over blocklist
const VALID_ROLES = ['user', 'admin', 'moderator'];
if (!VALID_ROLES.includes(input.role)) {
  throw new Error('Invalid role');
}

// Validate types and ranges
if (typeof id !== 'number' || id < 1) {
  throw new Error('Invalid ID');
}
```

## Secrets Management

### Don't
- Hardcode secrets in code
- Commit `.env` files
- Log secrets

### Do
- Use environment variables
- Use secret managers
- Rotate credentials regularly
- Add `.env` to `.gitignore`

## Security Checklist

- [ ] Input validation on all user input
- [ ] Output encoding for displayed data
- [ ] Parameterized database queries
- [ ] Authentication on protected routes
- [ ] Authorization checks
- [ ] HTTPS enforced
- [ ] Security headers set
- [ ] Dependencies audited
- [ ] Secrets not in code
- [ ] Logging without sensitive data
