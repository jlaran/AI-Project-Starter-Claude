# Contributing to AI Project Starter for Claude Code

Thank you for your interest in contributing! This document provides guidelines and instructions for contributing to this project.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [How to Contribute](#how-to-contribute)
- [Writing Guidelines](#writing-guidelines)
- [Pull Request Process](#pull-request-process)
- [Style Guide](#style-guide)

## Code of Conduct

By participating in this project, you agree to maintain a respectful and inclusive environment. We expect all contributors to:

- Be respectful and considerate in all interactions
- Welcome newcomers and help them get started
- Focus on constructive feedback
- Accept responsibility for mistakes and learn from them

## Getting Started

### Prerequisites

- Git installed on your machine
- A GitHub account
- Basic understanding of Markdown
- Familiarity with Claude Code (helpful but not required)

### Setup

1. **Fork the repository** on GitHub

2. **Clone your fork**:
   ```bash
   git clone https://github.com/YOUR_USERNAME/AI-Project-Starter-Claude.git
   cd AI-Project-Starter-Claude
   ```

3. **Add upstream remote**:
   ```bash
   git remote add upstream https://github.com/ORIGINAL_OWNER/AI-Project-Starter-Claude.git
   ```

4. **Keep your fork updated**:
   ```bash
   git fetch upstream
   git checkout main
   git merge upstream/main
   ```

## How to Contribute

### Types of Contributions

#### 1. New Agents (`.claude/agents/`)

Agents are specialized personas that Claude Code can adopt. Good agent contributions:

- Focus on a specific domain or expertise area
- Include clear guidelines and methodologies
- Provide actionable checklists
- Are stack-agnostic (work with any technology)

**Template:**
```markdown
# [Agent Name] Agent

You are a [role description]. Your role is to [responsibilities].

## Core Responsibilities
1. [Responsibility 1]
2. [Responsibility 2]

## Methodology
[How this agent approaches problems]

## Checklist
- [ ] Item 1
- [ ] Item 2

## Output Format
[Expected output structure]
```

#### 2. New Commands (`.claude/commands/`)

Commands are executable workflows. Good command contributions:

- Include YAML frontmatter with name, description, and tools
- Have clear step-by-step instructions
- Include actual executable bash commands
- Handle common edge cases

**Template:**
```markdown
---
name: command-name
description: What this command does
tools:
  - bash
---

# Command Title

Brief description of what this command accomplishes.

## Step 1: [Description]
\`\`\`bash
command here
\`\`\`

## Step 2: [Description]
\`\`\`bash
another command
\`\`\`
```

#### 3. New Skills (`.claude/skills/`)

Skills are reference guides for best practices. Good skill contributions:

- Cover a specific topic comprehensively
- Include practical examples
- Provide checklists for quick reference
- Are educational and actionable

**Template:**
```markdown
# [Skill Name] Skill

Brief description of what this skill covers.

## Key Concepts
[Core concepts explained]

## Best Practices
[Guidelines and recommendations]

## Examples
[Practical examples with code]

## Checklist
- [ ] Item 1
- [ ] Item 2
```

#### 4. Improvements to Existing Content

- Fix typos or grammatical errors
- Improve clarity or organization
- Add missing information
- Update outdated content

#### 5. Documentation

- Improve README
- Add examples
- Create tutorials
- Fix broken links

### Reporting Issues

Before creating an issue:

1. Search existing issues to avoid duplicates
2. Use a clear, descriptive title
3. Include relevant details:
   - What you expected to happen
   - What actually happened
   - Steps to reproduce (if applicable)

## Writing Guidelines

### Content Principles

1. **Be Stack-Agnostic**: Write content that works across different technologies
2. **Be Practical**: Include actionable steps and real commands
3. **Be Clear**: Use simple language and clear structure
4. **Be Complete**: Cover the topic thoroughly but concisely
5. **Be Consistent**: Follow existing patterns in the project

### Markdown Standards

- Use ATX-style headers (`#`, `##`, `###`)
- Use fenced code blocks with language specification
- Use tables for structured data
- Use task lists for checklists (`- [ ]`)
- Keep line length reasonable (< 120 characters)

### Naming Conventions

| Type | Convention | Example |
|------|------------|---------|
| Agent files | `kebab-case.md` | `code-reviewer.md` |
| Command files | `kebab-case.md` | `semantic-commit.md` |
| Skill files | `kebab-case.md` | `code-quality.md` |
| Headers | Title Case | `## Code Quality` |
| Code blocks | Specify language | ` ```bash ` |

## Pull Request Process

### Before Submitting

1. **Update your branch** with the latest from main:
   ```bash
   git fetch upstream
   git rebase upstream/main
   ```

2. **Test your changes** work correctly with Claude Code (if possible)

3. **Self-review** your changes for:
   - Spelling and grammar
   - Correct formatting
   - Working code examples
   - Consistency with existing content

### Creating the Pull Request

1. **Push your branch**:
   ```bash
   git push origin feat/your-feature-name
   ```

2. **Create the PR** on GitHub with:
   - Clear title following conventional commits: `feat(agents): add database-expert agent`
   - Description of what the PR adds/changes
   - Link to any related issues

### PR Title Convention

```
<type>(<scope>): <description>
```

| Type | When to Use |
|------|-------------|
| `feat` | New agent, command, or skill |
| `fix` | Bug fixes or corrections |
| `docs` | Documentation improvements |
| `refactor` | Restructuring without changing behavior |
| `chore` | Maintenance tasks |

**Examples:**
- `feat(agents): add database-expert agent`
- `fix(commands): correct git-branch syntax error`
- `docs(readme): add usage examples`

### After Submitting

- Respond to review feedback promptly
- Make requested changes in new commits
- Be patient - reviews take time

## Style Guide

### Voice and Tone

- Use second person ("You should...") for instructions
- Use imperative mood for commands ("Run this command")
- Be direct and concise
- Avoid jargon unless necessary (and explain when used)

### Code Examples

- Use realistic, practical examples
- Include comments for complex parts
- Show expected output where helpful
- Test all code examples before submitting

### Structure

- Start with a clear purpose statement
- Use headers to organize content logically
- Include a checklist for quick reference
- End with related resources or next steps

## Questions?

If you have questions about contributing:

1. Check existing documentation
2. Search closed issues and PRs
3. Open a new issue with the `question` label

Thank you for contributing to AI Project Starter for Claude Code!
