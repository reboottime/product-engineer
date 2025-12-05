---
description: Implement a feature from a feature file using git worktree workflow
argument-hint: [feature-file-path]
tags: [feature, implementation, worktree]
---

# Implement Feature with Git Worktree

**Working Directory:** `codebase/frontend`

**Feature File:** `$ARGUMENTS`

Spawn the frontend-engineer agent to implement the feature defined in `$ARGUMENTS` using git worktree workflow.

The agent should first read the feature file at `$ARGUMENTS` to understand requirements, then follow the implementation workflow below.

The agent should follow this workflow:

1. **Navigate to repo root:**

   ```bash
   cd $(git rev-parse --show-toplevel)
   ```

2. **Create worktree branch:**

   ```bash
   git worktree add -b feature/frontend-[feature-name] worktrees/frontend-[feature-name]
   ```

3. **Switch to worktree:**

   ```bash
   cd worktrees/frontend-[feature-name]/codebase/frontend
   ```

4. **Identify design doc:**
   - Check `/docs/product/design/screens/` for matching UI spec (e.g., `screens/login.md` for login page feature)
   - If no spec exists, ask user: "No design doc found for [feature]. Should I create one first or proceed with implementation?"
   - Read design patterns from `/docs/product/design/guides.design-patterns.md` for context

5. **Implement feature:**
   - Follow design patterns in `/docs/product/design/guides.design-patterns.md`
   - Reference terminology: `/docs/product/design/guides.terminology.md`
   - Follow Next.js guidelines in `./docs/guidelines/*.md`
   - Implement incrementally with regular commits
   - Test locally: `npm run dev`

6. **Commit changes:**

   ```bash
   git add .
   git commit -m "feat: [brief description]"
   ```

7. **Return to main worktree:**

   ```bash
   cd $(git rev-parse --show-toplevel)/codebase/frontend
   ```

8. **Merge when ready:**

   ```bash
   git merge feature/frontend-[feature-name]
   ```

9. **Cleanup worktree:**

   ```bash
   git worktree remove worktrees/frontend-[feature-name]
   git branch -d feature/frontend-[feature-name]
   ```

## Key Rules

- Always work in a feature worktree, never directly on main
- One feature = one worktree branch
- Keep commits small and focused
- Test before merging back to main
- Clean up worktrees after merging

## Example

User: `/implement-feature docs/features/login.md`

Assistant creates: `git worktree add -b feature/frontend-login worktrees/frontend-login` (from repo root)
