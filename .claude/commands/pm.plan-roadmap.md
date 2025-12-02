---
description: Create or update Now/Next/Later product roadmap
tags: [product, roadmap, pm, planning]
agent: product-manager
---

# Plan Roadmap

You are the product-manager agent. human needs you to create or update the product roadmap.

## Your Task

Create/update the Now/Next/Later roadmap with clear prioritization using Impact/Effort scoring.

## Workflow

1. **Gather context**:
   - Read `/Claude.md` (current phase, metrics, principles)
   - Try Read `docs/product/roadmap.md` (existing roadmap)
   - Glob: `docs/product/requirements/*.md` (all PRDs)
   - Glob: `docs/product/research/*.md` and `docs/product/decisions/*-validation.md` (insights, validations)

2. **Ask human** using AskUserQuestion:
   - **Business goals**: Acquire users / Retain users / Generate revenue / Validate learning (multiSelect)
   - **Team capacity**: 1-2 eng weeks/month / 4-8 / 12+
   - **Strategy**: Strategic bets / Quick wins / Balanced mix

3. **Score each feature** (Impact/Effort framework):
   - **Impact** (1-10): Acquisition (0-3) + Retention (0-3) + Revenue (0-3) + Strategic Fit (1-3)
     - Normalize to 1-10: (Total / 12) × 10
   - **Effort** (3-10): Eng weeks (1-4) + Complexity (1-3) + Dependencies (1-3)
   - **Priority Score**: Impact / Effort (higher is better)

4. **Categorize features** (Now/Next/Later):
   - **NOW** (1-3 items max): Priority >1.5 AND aligned with goals AND within capacity
   - **NEXT** (3-5 items): Priority 0.8-1.5, validated, logical sequence
   - **LATER** (5-10 items): Priority 0.3-0.8, needs validation or lower priority
   - **NOT DOING**: Priority <0.3 OR misaligned with strategy

5. **Write/update roadmap** at `/docs/product/roadmap.md`

6. **Verify**:
   - NOW has 1-3 items (not more)
   - Each item has Problem, Why Now/Next/Later, Success metrics
   - NOT DOING has explicit rejections
   - Priority scores shown

## Output

`/docs/product/roadmap.md`

## Template

```markdown
# Product Roadmap

**Last Updated**: YYYY-MM-DD
**Phase**: [Customer Discovery / POC / MVP / Production]
**Team Capacity**: [X eng weeks/month]
**Current Goals**: [List from human]

## Prioritization Framework

**Impact** (1-10): Acquisition + Retention + Revenue + Strategic Fit
**Effort** (1-10): Eng Weeks + Complexity + Dependencies
**Priority Score** = Impact / Effort

## Now (Current Focus)

**Capacity Allocation**: [X of Y weeks allocated]

### [Feature 1] - Priority: [Score]
- **Problem**: [User problem this solves]
- **Impact**: [Score/10] - [Why high impact]
- **Effort**: [Score/10] - [Estimated weeks]
- **Why Now**: [Business goal alignment]
- **Success**: [Metric and target]

### [Feature 2] - Priority: [Score]
- **Problem**: [User problem]
- **Impact**: [Score/10]
- **Effort**: [Score/10]
- **Why Now**: [Business goal alignment]
- **Success**: [Metric and target]

## Next (Validated, Ready to Build)

### [Feature 3] - Priority: [Score]
- **Problem**: [User problem]
- **Impact**: [Score/10]
- **Effort**: [Score/10]
- **Why Next**: [Why sequenced here - dependencies, priorities]
- **Success**: [Metric and target]

## Later (Under Consideration)

### [Idea 1] - Priority: [Score]
- **Problem**: [User problem]
- **Impact**: [Score/10]
- **Effort**: [Score/10]
- **Why Later**: [Why deprioritized]
- **Validation Needed**: [What needs to be true to promote]

## Not Doing (And Why)

- **[Feature]** (Priority: [Score]): [Why we said no]
- **[Feature]** (Priority: [Score]): [Why we said no]

## Roadmap Notes

**Assumptions**:
- [Key assumption about capacity/market/users]

**Dependencies**:
- [Feature X depends on Feature Y]

**Review Schedule**: [Date or milestone for next review]
```

## Notes

- NOW: Max 3 items (focus is critical)
- Capacity: Never over-allocate
- Strategic fit mandatory for NOW
- Sequence by dependencies
- Balance strategic vs quick wins per human's preference
- Saying "no" prevents waste
