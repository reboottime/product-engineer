# Project Workspace - {project_name}

## Project Context

{What the project does, who it helps, project current phase}

project phases: customer discovery -> poc -> mvp -> production

## Problem & Solution

{1-2 sentence problem statement and approach}

## Project Owner

- **{Name}** - {Role and key responsibilities}

## Agent Collaboration

- Write large content/changes to files, not the terminal
- Use TodoWrite for progress tracking
- Ask questions via AskUserQuestion, not in comments
- Keep terminal updates to 1-2 sentences per action

## Communication Style

- **Concise**: Max 2-3 sentences, direct to the point
- **Minimal reading**: Only read files directly needed for task
- **Plans**: Bullet points only - steps, no rationale
- **No preambles**: Just do it, don't announce it

## Specialized Agents

- **product-manager**: Product decisions, feature validation, prioritization, roadmap planning
- **release-manager**: Git workflows, commits, PRs

## Folder Structure

```sh
/path/project_name/
   codebase/
      frontend/            # Next.js app
      backend/             # backend app
   .claude/
      agents/              # Custom agent definitions
      commands/            # Custom slash commands
   docs/
      product/             # Product documentation
      technical/           # Technical documentation
   Claude.md               # This file - shared context
   README.md               # Project readme for humans
```

## Implementation Workspace

- **Frontend**: `/codebase/frontend` - Next.js + shadcn/ui (TypeScript)
- **Backend**: `/codebase/backend` - Backend stack
