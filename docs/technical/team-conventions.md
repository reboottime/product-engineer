# Team Conventions

**Status:** Active
**Applies to:** All team members (human and ai agents, etc.)
**Last Updated:** 2025-11-29

## Overview

This document defines **project-specific** team conventions. Follow these rules for git workflow, commits, and PRs. General best practices (conventional commits, clean git history, etc.) are assumed knowledge.

**Current Sections:**

- Git Workflow (branching, commits, PRs)
- *(More sections added as team practices evolve)*

---

# Git Workflow

## Key Principles

- **Atomic Commits**: Each commit should represent a single logical change
- **Meaningful Messages**: Commit messages should explain why, not just what changed
- **Clean History**: Keep git history linear and easy to follow
- **Automatic but Safe**: Automate commits but never force push or overwrite history without explicit permission
- **Branch Awareness**: Always know which branch you're on and follow the project's branching strategy

## Security Rules (Required)

**NEVER commit secrets or sensitive data:**

- `.env` files (use `.env.example` instead)
- API keys, tokens, credentials
- Passwords or authentication secrets
- Private certificates or keys
- Database connection strings with credentials

**If accidentally committed:** Rotate the secret immediately and use `git filter-branch` or BFG Repo-Cleaner to remove from history.

## Branch Naming (Required)

```bash
feature/short-description    # New features
bugfix/short-description     # Bug fixes
hotfix/short-description     # Urgent production fixes
```

**Examples:**

- `feature/user-authentication`
- `bugfix/login-redirect-loop`
- `hotfix/critical-security-patch`

## Commit Message Format (Required)

Use [Conventional Commits](https://www.conventionalcommits.org/) with **required Claude Code footer**:

```
type(scope): Short description (max 72 chars)

Optional body explaining why (not what).

🤖 Generated with [Claude Code](https://claude.com/claude-code)

Co-Authored-By: Claude <noreply@anthropic.com>
```

### Commit Types (Enforced)

| Type | When to Use | Example |
|------|-------------|---------|
| `feat` | New feature | `feat(auth): add JWT authentication` |
| `fix` | Bug fix | `fix(login): resolve redirect loop` |
| `docs` | Documentation changes | `docs(readme): update setup instructions` |
| `style` | Code formatting, no logic changes | `style(components): fix indentation` |
| `refactor` | Code refactoring | `refactor(api): simplify error handling` |
| `test` | Adding or updating tests | `test(auth): add login flow tests` |
| `chore` | Maintenance tasks, dependencies, config | `chore(deps): update react to 18.3` |
| `merge` | Merging branches | `merge: feature/auth into main` |

### Examples

```bash
feat(auth): add JWT authentication

Implements authentication using JWT tokens with 7-day expiration.
Users stay logged in across sessions.

🤖 Generated with [Claude Code](https://claude.com/claude-code)

Co-Authored-By: Claude <noreply@anthropic.com>
```

```bash
fix(login): resolve redirect loop on logout

Added session cleanup to prevent stale tokens causing redirect loops.

🤖 Generated with [Claude Code](https://claude.com/claude-code)

Co-Authored-By: Claude <noreply@anthropic.com>
```

## Push Strategy (Default Behavior)

**Feature/bugfix/hotfix branches:**

- ✅ Automatically push after commit
- Enables backup and team visibility

**Main/master branch:**

- ⚠️ Commit locally, ask before pushing
- Typically push via PR merge, not direct commits

## PR Template (Required)

```markdown
## Summary
- Bullet points of what changed

## Why
Brief explanation of the problem this solves

## Test Plan
- [ ] Tested on mobile viewport
- [ ] Tested on desktop viewport
- [ ] TypeScript builds without errors
- [ ] No console errors

## Screenshots (if UI changes)
[Add screenshots]

🤖 Generated with [Claude Code](https://claude.com/claude-code)
```

## Special Cases

### Hotfixes (Production Emergencies)

1. Create `hotfix/description` branch from main/master
2. Fix with minimal changes
3. Get expedited review
4. Merge and deploy immediately
5. Communicate to team

### Merge Conflicts

- Resolve in your editor, test thoroughly
- For complex conflicts, ask release-manager for help

---

**Note:** This is a living document. Update as conventions evolve.
