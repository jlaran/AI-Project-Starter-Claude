# Code Quality Skill

Standards and practices for maintaining high-quality code.

## SOLID Principles

### Single Responsibility
Each class/function should have one reason to change.

❌ Bad:
```typescript
class User {
  save() { /* database logic */ }
  sendEmail() { /* email logic */ }
  generateReport() { /* report logic */ }
}
```

✅ Good:
```typescript
class User { /* user data only */ }
class UserRepository { save(user) {} }
class EmailService { send(user, template) {} }
class ReportGenerator { generate(user) {} }
```

### Open/Closed
Open for extension, closed for modification.

### Liskov Substitution
Subtypes must be substitutable for base types.

### Interface Segregation
Many specific interfaces over one general interface.

### Dependency Inversion
Depend on abstractions, not concretions.

## Clean Code Rules

### Functions
- Single purpose
- Less than 20 lines
- Few parameters (max 3)
- Descriptive names
- No side effects

### Naming
- Variables: describe what it holds
- Functions: describe what it does
- Classes: describe what it is
- Use domain vocabulary

### Comments
- Explain *why*, not *what*
- Keep up to date
- Prefer self-documenting code

## Code Smells

| Smell | Problem | Solution |
|-------|---------|----------|
| Long method | Hard to understand | Extract methods |
| Large class | Too many responsibilities | Split into classes |
| Long parameter list | Hard to call correctly | Use object parameter |
| Duplicate code | Change in multiple places | Extract shared code |
| Deep nesting | Hard to follow | Early returns, extract |
| Magic numbers | Unclear meaning | Named constants |

## Quality Checklist

- [ ] Functions are small and focused
- [ ] Names are clear and descriptive
- [ ] No duplication
- [ ] Error handling is appropriate
- [ ] Tests cover critical paths
- [ ] No dead code
