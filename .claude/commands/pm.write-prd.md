---
description: Create detailed product requirements document for a validated feature
tags: [product, prd, requirements, pm]
agent: product-manager
---

# Write PRD

You are the product-manager agent. human needs you to write a Product Requirements Document (PRD) for a feature.

## Your Task

Create a PRD that defines WHAT to build and WHY, so product-design-lead can design HOW.

## Arguments

`[feature-name]` - Feature to write PRD for

## Workflow

1. **Verify validation**:
   - Try Read `/docs/product/decisions/[feature-name]-validation.md`
   - If exists: Check decision was "Build Now"
   - If not found: Ask human if feature was validated
   - If "Build Later" or "Don't Build": Warn human

2. **Gather context**:
   - Read `/Claude.md` (context, metrics, principles)
   - Read validation doc (if exists)
   - Grep `[feature-name]` in `docs/product/research` and `docs/product`

3. **Ask human to clarify** using AskUserQuestion:
   - **Constraints**: Budget/time / Technical / Compliance / None
   - **Edge cases**: Standard use cases only / Yes, I'll specify
   - **Additional context**: Anything else to include?

4. **Write PRD** at `/docs/product/requirements/[feature-name].md`

5. **Verify quality**:
   - Problem statement clear (1-2 sentences)
   - User stories specific
   - Success metrics measurable
   - North Star defined
   - Out of scope explicit
   - Must Have vs Nice to Have separated
   - Document is 1-2 pages max

6. **Offer next step**:
   - Ask human: "Should I spawn product-design-lead to create UX design?"
   - If yes: Use Task tool with subagent_type=product-design-lead

## Output

`/docs/product/requirements/[feature-name].md`

## Template

```markdown
# [Feature Name] - Requirements

**Status**: Draft / Final
**Owner**: [human or team member]
**Target**: Now / Next / Later
**Last Updated**: YYYY-MM-DD

## Problem Statement

[1-2 sentences: What problem this solves and why it matters]

## User Stories

1. As a [user type], I want to [action], so that [benefit]
2. As a [user type], I want to [action], so that [benefit]
3. As a [user type], I want to [action], so that [benefit]

## Success Metrics

**North Star**: [Primary metric]

**Supporting Metrics**:
- [Metric 1]: [Target]
- [Metric 2]: [Target]
- [Metric 3]: [Target]

**How We'll Measure**: [Tracking setup needed]

## Requirements

### Must Have (MVP)

- [ ] [Specific requirement]
- [ ] [Specific requirement]
- [ ] [Specific requirement]

**Acceptance Criteria**: [How we know MVP is complete]

### Nice to Have (Post-MVP)

- [ ] [Enhancement]
- [ ] [Enhancement]

## Out of Scope

- **[Feature/capability]**: Why not now / Maybe later when [condition]
- **[Feature/capability]**: Why not now / Maybe later when [condition]

## User Flow

**Happy Path**:
1. User [action] → System [response]
2. User [action] → System [response]
3. User [action] → System [response]

**Edge Cases**:
- [Scenario]: [Behavior]
- [Scenario]: [Behavior]

## Technical Considerations

**Dependencies**: [Existing features/services needed]
**Constraints**: [Limitations - offline, performance, platform]
**Data/Privacy**: [What data collected, how stored, compliance]

## Open Questions

- [ ] [Question needing answer before/during implementation]
- [ ] [Question needing answer before/during implementation]

## Design Notes

**Key Principles** (from Claude.md):
- [Relevant principle 1]
- [Relevant principle 2]

**UX Considerations**: [Key UX challenge or focus]

## Risks

**Risk**: [What could go wrong]
- **Likelihood**: High / Medium / Low
- **Impact**: High / Medium / Low
- **Mitigation**: [How to reduce risk]

## Launch

**Definition of Done**:
- [ ] [Criteria for "launched"]
- [ ] [Criteria for "launched"]

**Rollout**: [All users / Gradual / Beta?]
**Post-Launch**: Review metrics after [timeframe], use `/pm.review-feature [feature-name]`

## References

- Validation: [Link if exists]
- Research: [Links to docs]
```
