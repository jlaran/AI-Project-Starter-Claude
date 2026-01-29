<p align="center">
  <h1 align="center">AI Project Starter for Claude Code</h1>
  <p align="center">
    Pre-built agents, skills, and commands to supercharge your development workflow
  </p>
</p>

<p align="center">
  <a href="https://claude.ai/claude-code"><img src="https://img.shields.io/badge/Claude%20Code-Compatible-blueviolet?style=for-the-badge" alt="Claude Code Compatible"></a>
  <a href="./LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" alt="MIT License"></a>
  <a href="./CONTRIBUTING.md"><img src="https://img.shields.io/badge/PRs-Welcome-brightgreen?style=for-the-badge" alt="PRs Welcome"></a>
</p>

<p align="center">
  <a href="./.claude/agents"><img src="https://img.shields.io/badge/Agents-10-blue?style=flat-square" alt="10 Agents"></a>
  <a href="./.claude/commands"><img src="https://img.shields.io/badge/Commands-6-orange?style=flat-square" alt="6 Commands"></a>
  <a href="./.claude/skills"><img src="https://img.shields.io/badge/Skills-6-green?style=flat-square" alt="6 Skills"></a>
</p>

---

A curated collection of professional development configurations for [Claude Code](https://claude.ai/claude-code). Copy to any project to instantly gain access to expert code review, security auditing, git workflows, and more.

## Table of Contents

- [Quick Start](#quick-start)
- [Features](#features)
- [Usage](#usage)
- [Customization](#customization)
- [Contributing](#contributing)
- [License](#license)

## Quick Start

**Option 1:** Copy the `.claude` directory to your existing project:

```bash
cp -r .claude /path/to/your/project/
```

**Option 2:** Clone and use as a starting point:

```bash
git clone https://github.com/jlaran/AI-Project-Starter-Claude.git my-project
cd my-project
```

That's it. Start using the commands in Claude Code immediately.

## Features

### Agents

Specialized personas with domain expertise that Claude Code can adopt for specific tasks.

| Agent | Description |
|:------|:------------|
| **project-orchestrator** | Coordinates complex tasks across domains and specialists |
| **code-reviewer** | Thorough code reviews with security focus and constructive feedback |
| **architect** | System design, technology decisions, and architectural patterns |
| **debugger** | Systematic bug hunting and root cause analysis |
| **security-auditor** | OWASP-based vulnerability detection and security best practices |
| **git-expert** | Professional git workflows, commits, branches, and PRs |
| **project-maintainer** | Code hygiene, documentation, and project organization |
| **ux-expert** | User experience, usability, and user flow optimization |
| **designer** | UI/visual design, design systems, and component specifications |
| **information-architect** | Content structure, navigation, and taxonomy design |

### Commands

Executable workflows with step-by-step instructions and bash commands.

| Command | Description |
|:--------|:------------|
| `/semantic-commit` | Analyze staged changes and create conventional commit messages |
| `/git-branch` | Create properly named feature branches |
| `/create-pr` | Generate comprehensive pull requests with documentation |
| `/code-review` | Perform thorough code reviews against best practices |
| `/security-scan` | Scan codebase for security vulnerabilities |
| `/project-audit` | Audit project health, organization, and documentation |

### Skills

Reference guides for best practices and methodologies.

| Skill | Description |
|:------|:------------|
| **debugging** | Systematic debugging methodology and techniques |
| **code-quality** | SOLID principles, clean code, and code smells |
| **testing** | Test writing best practices and patterns |
| **documentation** | Documentation standards and templates |
| **git-workflow** | Git conventions, branching strategies, and workflows |
| **security** | Security best practices and OWASP guidelines |

## Usage

### Using Agents

Reference an agent to have Claude Code adopt that persona:

```
Review this code as a security auditor
```

```
Help me debug this issue using systematic debugging
```

```
As an architect, design the authentication system for this app
```

### Using Commands

Invoke commands directly with the slash syntax:

```
/semantic-commit
```

```
/security-scan
```

```
/project-audit
```

### Using Skills

Reference skills for guidance on specific topics:

```
Apply the code-quality skill to review this function
```

```
Following the git-workflow skill, help me resolve this merge conflict
```

## Customization

### Project-Specific Context

Create a `CLAUDE.md` file in your project root to provide context:

```markdown
# Project Context

This is a Node.js/Express API for e-commerce.

## Tech Stack
- Node.js 20 with TypeScript
- PostgreSQL with Prisma ORM
- Redis for caching
- Jest for testing

## Conventions
- Use camelCase for variables and functions
- All API endpoints under /api/v1
- Tests alongside source files (*.test.ts)
```

### Adding Custom Agents

Create markdown files in `.claude/agents/`:

```markdown
# My Custom Agent

You are a specialist in [domain]. Your responsibilities include [list].

## Guidelines
- [Guideline 1]
- [Guideline 2]

## Checklist
- [ ] Task 1
- [ ] Task 2
```

### Adding Custom Commands

Create markdown files in `.claude/commands/` with YAML frontmatter:

~~~markdown
---
name: my-command
description: What this command does
tools:
  - bash
---

# Command Title

## Step 1: Description
```bash
command here
```
~~~

## Directory Structure

```
.claude/
├── agents/                    # Specialist personas
│   ├── project-orchestrator.md
│   ├── code-reviewer.md
│   ├── architect.md
│   ├── debugger.md
│   ├── security-auditor.md
│   ├── git-expert.md
│   ├── project-maintainer.md
│   ├── ux-expert.md
│   ├── designer.md
│   └── information-architect.md
├── commands/                  # Executable workflows
│   ├── semantic-commit.md
│   ├── git-branch.md
│   ├── create-pr.md
│   ├── code-review.md
│   ├── security-scan.md
│   └── project-audit.md
└── skills/                    # Reference guides
    ├── debugging.md
    ├── code-quality.md
    ├── testing.md
    ├── documentation.md
    ├── git-workflow.md
    └── security.md
```

## Contributing

We welcome contributions from the community. Whether it's a new agent, command, skill, or improvements to existing content, your input helps make this project better.

See our **[Contributing Guide](./CONTRIBUTING.md)** for detailed instructions.

### Quick Start for Contributors

```bash
# Fork and clone
git clone https://github.com/jlaran/AI-Project-Starter-Claude.git

# Create a branch
git checkout -b feat/my-new-agent

# Make changes and commit
git commit -m "feat(agents): add database-expert agent"

# Push and create PR
git push origin feat/my-new-agent
```

### Contribution Ideas

We're looking for contributions in these areas:

**Agents:** `database-expert`, `api-designer`, `performance-optimizer`, `accessibility-auditor`, `devops-engineer`

**Commands:** `/changelog`, `/release`, `/dependency-update`, `/lint-fix`, `/test-coverage`

**Skills:** `api-design`, `database`, `performance`, `accessibility`, `ci-cd`

## Best Practices

| Practice | Description |
|:---------|:------------|
| **Stay focused** | Each agent should have a clear, single specialty |
| **Be executable** | Commands should include actual runnable bash commands |
| **Be reference-able** | Skills should serve as quick-reference guides |
| **Stay stack-agnostic** | Content should work across different tech stacks |
| **Version control** | Keep your `.claude` directory in git |

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

---

<p align="center">
  Built for <a href="https://claude.ai/claude-code">Claude Code</a> by <a href="https://anthropic.com">Anthropic</a>
</p>
