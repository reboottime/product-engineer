---
description: Sets up product sections in Claude.md for new project (problem, solution, metrics, phase)
tags: [product, setup, pm]
agent: product-manager
---

# Define Project Context

You are the product-manager agent. human is starting a new project and needs you to set up the product sections in Claude.md.

## Your Task

Create or update product sections in `/Claude.md`:

- Project Context (what it does, who it helps, current phase)
- Problem & Solution (1-2 sentence statement)
- Success Metrics (North Star + Key Metrics)
- Key Design Principles (3-5 product-specific principles)

## Workflow

1. **Gather existing context**:
   - Try Read `/Claude.md` (may have some info)
   - Try Read `/README.md` (may have project description)
   - Use Glob: `docs/**/*.md` (see what docs exist)

2. **Research market autonomously**:
   - Based on project name and existing docs
   - WebSearch: "[project domain] user problems 2025", "[project domain] market trends", "best practices [project domain]"
   - Draft: Problem hypothesis, target users, market context

3. **Ask human** using AskUserQuestion:
   - **Phase**: Customer Discovery / POC / MVP / Production
   - **Problem**: Present hypothesis, ask if accurate (Yes / Partially / No)
   - **Target User**: [Options from research] / Other
   - **Success**: User engagement / User outcomes / Revenue / Learning (early stage)

4. **Draft product sections**:
   - **Project Context**: [name] helps [users] [achieve outcome]. Currently in [phase] phase.
   - **Problem & Solution**: 1-2 sentence statement
   - **Success Metrics**: North Star + 3 supporting metrics (appropriate for phase)
   - **Key Design Principles**: 3-5 principles from research + human's input

5. **Review draft with human** using AskUserQuestion:
   - Show draft sections, ask: "Should I proceed with updating Claude.md?"
   - Options: Yes, looks good / Needs refinement
   - If refinement: Ask what to change, revise, ask again

6. **Update Claude.md**:
   - If exists: Use Edit tool to update product sections
   - If doesn't exist: Use Write tool to create it
   - Preserve technical sections

7. **Verify**:
   - All sections added (Project Context, Problem & Solution, Success Metrics, Design Principles)

## Output

Product sections added/updated in `/Claude.md`

## Notes

**Metrics by Phase**:

- **Discovery**: Learning metrics (interviews conducted, insights gathered)
- **POC**: Feasibility metrics (technical validation, user interest)
- **MVP**: Engagement metrics (DAU, retention, core action completion)
- **Production**: Business metrics (revenue, growth, retention at scale)

**Design Principles Should Be**:

- Specific to domain (not generic like "make it simple")
- Actionable (guide actual design decisions)
- Rooted in user needs or market insights
