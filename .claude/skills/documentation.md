# Documentation Skill

Guidelines for writing clear, maintainable documentation.

## Documentation Types

### Code Comments
```typescript
// Explain WHY, not WHAT
// Bad: Increment counter
// Good: Track retries to avoid infinite loop

/**
 * Calculates shipping cost based on weight and destination.
 *
 * @param weight - Package weight in kg
 * @param zone - Shipping zone (1-5)
 * @returns Cost in cents
 * @throws {InvalidZoneError} If zone is outside 1-5 range
 */
function calculateShipping(weight: number, zone: number): number
```

### README Structure
1. Project name and description
2. Quick start (install, run)
3. Prerequisites
4. Configuration
5. Usage examples
6. Project structure
7. Contributing
8. License

### API Documentation
- Endpoint URL and method
- Request parameters
- Request body schema
- Response schema
- Error responses
- Example requests

## Writing Guidelines

### Be Concise
- Short sentences
- Active voice
- Remove filler words

### Be Specific
❌ "Configure the settings appropriately"
✅ "Set `MAX_CONNECTIONS` to 100 in `.env`"

### Use Examples
Show, don't just tell:
```bash
# Install dependencies
npm install

# Run development server
npm run dev
```

### Keep Updated
- Review docs with code changes
- Date-stamp time-sensitive info
- Remove outdated content

## README Template

```markdown
# Project Name

One-line description of what this does.

## Quick Start

\`\`\`bash
npm install
npm start
\`\`\`

## Prerequisites

- Node.js >= 18
- PostgreSQL 14+

## Configuration

| Variable | Description | Default |
|----------|-------------|---------|
| `PORT` | Server port | 3000 |
| `DB_URL` | Database connection | - |

## Usage

[Show common use cases]

## API Reference

### GET /users
Returns list of users.

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md)

## License

MIT
```

## Documentation Checklist

- [ ] README explains what and why
- [ ] Setup instructions are complete
- [ ] Environment variables documented
- [ ] API endpoints documented
- [ ] Complex code has comments
- [ ] Examples provided
- [ ] No outdated information
