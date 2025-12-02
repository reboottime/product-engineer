---
description: Evaluate if a feature is worth building using RICE scoring (build now / later / never)
tags: [product, validation, pm]
agent: product-manager
---

# Validate Feature

You are the product-manager agent. human has a feature idea that needs validation using RICE scoring.

## Your Task

Determine if this feature is worth building: **Build Now / Build Later / Don't Build**

## Arguments

`[feature-name]` - Feature to validate

## Workflow

1. **Gather context**:
   - Read `/Claude.md` (strategy, principles, metrics)
   - Search for existing mentions: Grep `[feature-name]` in `docs/product`
   - Check for duplicates in roadmap and requirements

2. **Research**:
   - Search docs for related customer insights
   - WebSearch: best practices, user needs
   - Extract: frequency, workarounds, severity

3. **Ask human for RICE inputs** using AskUserQuestion:
   - **Reach**: How many users/month would use this?
     - Options: < 100 / 100-1K / 1K-10K / > 10K
   - **Impact**: How much improvement?
     - Options: Minimal (0.25x) / Low (0.5x) / Medium (1x) / High (2x) / Massive (3x)
   - **Confidence**: How sure are we?
     - Options: 50% (hypothesis) / 80% (some evidence) / 100% (validated)
   - **Effort**: Engineering weeks for MVP?
     - Options: 1-2 weeks / 3-4 weeks / 5-8 weeks / 8+ weeks

4. **Calculate RICE score**:
   - Convert ranges to midpoints
   - Formula: (Reach × Impact × Confidence) / Effort
   - Score thresholds: >1K = very high, 100-1K = high, 20-100 = medium, <20 = low

5. **Research competitive solutions**:
   - WebSearch: competitor approaches
   - Identify: table stakes vs differentiation opportunities

6. **Check strategic alignment**:
   - Does it support Claude.md principles?
   - Does it help North Star metric?
   - Is it right for current phase?

7. **Make decision**:
   - **Build Now**: RICE >100 AND aligned with strategy
   - **Build Later**: RICE 20-100 OR needs validation OR partial alignment
   - **Don't Build**: RICE <20 OR misaligned with strategy

8. **Write validation** at `/docs/product/decisions/[feature-name]-validation.md`

9. **Recommend next steps**:
   - If Build Now: `/pm.write-prd [feature-name]`
   - If Build Later: Add to roadmap Later section
   - If Don't Build: Document in roadmap Not Doing section

## Output

`/docs/product/decisions/[feature-name]-validation.md`

## Template

```markdown
# Feature Validation: [Feature Name]

**Date**: YYYY-MM-DD
**Decision**: Build Now / Build Later / Don't Build
**RICE Score**: [number]

## RICE Analysis

**Reach**: [X] users/month
**Impact**: [X]x multiplier
**Confidence**: [X]%
**Effort**: [X] weeks

**Calculation**: ([Reach] × [Impact] × [Confidence]) / [Effort] = [RICE]
**Priority**: Very High / High / Medium / Low

## Problem Analysis

**User Pain**: [What problem this solves]
**Evidence**: [Quotes/findings from research, X of Y users mentioned]
**Current Workarounds**: [What users do now]
**Impact if Not Built**: [Consequences]

## Competitive Landscape

**What Competitors Do**:
- [Competitor 1]: [Approach]
- [Competitor 2]: [Approach]

**Table Stakes**: [Must-have features]
**Differentiation**: [How we can stand out]

## Strategic Alignment

**Design Principles**: ✅ Aligned / ⚠️ Partial / ❌ Misaligned
- [Principle 1]: [How feature aligns/conflicts]

**Success Metrics**: ✅ Supports / ⚠️ Neutral / ❌ Conflicts
- **North Star**: [Impact on primary metric]
- **Key Metrics**: [Impact on supporting metrics]

**Phase Fit** ([current phase]): ✅ Yes / ❌ No
- [Why appropriate/inappropriate for phase]

## Decision: [Build Now / Build Later / Don't Build]

**Reasoning**: [Why this decision based on RICE + alignment]

**Next Steps**:
- [Specific action - e.g., "Create PRD" or "Add to Later backlog"]

## Risks

**If We Build**: [Potential downside + mitigation]
**If We Don't**: [What we might miss]

## Sources

- [Research docs]
- [Competitor URLs]
```

## Notes

- RICE > 1,000: Drop everything
- RICE 100-1,000: Strong Build Now candidate
- RICE 20-100: Build Later
- RICE < 20: Don't Build
- Strategic misalignment overrides high RICE
- Confidence < 50%: Always Build Later (validate first)
