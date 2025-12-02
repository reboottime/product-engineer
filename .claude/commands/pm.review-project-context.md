---
description: Quarterly review and update of product strategy in Claude.md
tags: [product, review, pm]
agent: product-manager
---

# Review Project Context

You are the product-manager agent. human needs you to review and update the product sections in Claude.md.

## Your Task

Review and update product sections in `/Claude.md` to ensure they're still accurate.

## When to Use

- Every quarter (maintenance)
- After major pivot or learning
- Phase transitions (Customer Discovery → POC, etc.)

## Workflow

1. **Gather context**:
   - Read `/Claude.md`
   - Glob: `docs/product/roadmap.md`, `docs/product/requirements/*.md`, `docs/product/research/*.md`
   - Extract current: Project Context, Problem & Solution, Success Metrics, Design Principles

2. **Ask human** using AskUserQuestion:
   - **Problem**: Still accurate / Evolved based on learnings / Major pivot
   - **Phase**: Stay in [current] / Move to next phase
   - **Metrics**: Still relevant / Need to adjust targets / Need different metrics
   - **Principles**: Still guiding us / Need refinement / Need new principles

3. **Validate phase transition** (if human wants to move):
   - **Discovery → POC**: Check for 3+ customer insights, validated problem
   - **POC → MVP**: Check for POC documentation, technical feasibility proven
   - **MVP → Production**: Check for MVP metrics, real user usage
   - If not ready: Warn human

4. **Review artifact alignment**:
   - **Roadmap**: Do items align with Claude.md priorities?
   - **PRDs**: Do they address Claude.md problem statement?
   - **Research**: Does it validate Claude.md assumptions?
   - Identify misalignments

5. **Recommend updates**:
   - **Problem & Solution**: Keep same / Update to: [X]
   - **Phase**: Keep same / Update to: [X]
   - **Success Metrics**: Keep same / Update to: [X]
   - **Design Principles**: Keep same / Update to: [X]
   - For each change, explain why

6. **Review with human** using AskUserQuestion:
   - Show recommendations, ask: "Should I proceed with updating?"
   - Options: Yes, update / No changes needed / Adjust recommendations

7. **Update Claude.md** (if approved):
   - Edit only product sections
   - Preserve technical sections

8. **Verify**:
   - Updates applied correctly
   - No unintended changes to other sections

## Output

Updated product sections in `/Claude.md` (or confirmation no changes needed)

## Notes

**Phase Transition Checklist**:
- **Discovery → POC**: 5+ interviews, 3+ insights, problem validated
- **POC → MVP**: POC demonstrated, technical feasibility proven, MVP scope defined
- **MVP → Production**: MVP launched, metrics tracked, positive PMF indicators

**When NOT to Update**:
- If it's working (still guiding team correctly)
- Too frequent (don't update more than quarterly)
- Minor tweaks (small wording changes)
- No new learnings
