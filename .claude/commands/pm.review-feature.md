---
description: Post-launch metrics review and iteration recommendations (2-4 weeks after launch)
tags: [product, post-launch, pm, metrics, review]
agent: product-manager
---

# Review Feature

You are the product-manager agent. human needs you to review a launched feature's performance.

## Your Task

Analyze feature performance against target metrics and recommend: **Iterate / Pivot / Sunset / Expand**

## Arguments

`[feature-name]` - Feature to review

## When to Use

2-4 weeks after feature launch (enough time for meaningful data)

## Workflow

1. **Find the PRD**:
   - Try Read `/docs/product/requirements/[feature-name].md`
   - If not found: Use Glob `docs/product/requirements/*.md` and search content
   - Extract target metrics (North Star + supporting metrics)

2. **Ask human for actual performance** using AskUserQuestion:
   - **North Star**: Met/exceeded / Missed / Don't have data
   - **Metrics**: I'll provide numbers / No data collected
   - **Feedback**: Yes I have feedback / No / Mixed

3. **Search for user feedback**:
   - Grep `[feature-name]` in `docs/product/research` and `docs/product/feedback`
   - Extract: quotes, complaints, praise

4. **Analyze performance**:
   - For each metric: Target vs Actual, Status (✅ Met / ❌ Missed / 🎉 Exceeded)
   - What worked? What didn't? Unexpected behavior? User sentiment?

5. **Make recommendation**:
   - **Iterate**: North Star ✅ met, mostly positive feedback → specific tweaks
   - **Expand**: North Star 🎉 exceeded, strong positive → build related features
   - **Pivot**: North Star ❌ missed BUT discovered new use case → adjust approach
   - **Sunset**: North Star ❌ missed, negative/absent feedback, no path forward → remove

6. **Write post-mortem** at `/docs/product/post-mortems/[feature-name]-review.md`

7. **Verify**:
   - Target vs Actual for all metrics
   - What worked and didn't sections have content
   - Recommendation has specific next steps
   - Honest assessment (not sugar-coated)

## Output

`/docs/product/post-mortems/[feature-name]-review.md`

## Template

```markdown
# Post-Launch Review: [Feature Name]

**Launch Date**: YYYY-MM-DD
**Review Date**: YYYY-MM-DD
**Recommendation**: Iterate / Expand / Pivot / Sunset

## Target Metrics (from PRD)

**North Star**: [Target metric and goal]
**Supporting Metrics**:
- [Metric 1]: [Target]
- [Metric 2]: [Target]

## Actual Performance

**North Star**: [Actual] ✅ Met / ❌ Missed / 🎉 Exceeded

**Supporting Metrics**:
- [Metric 1]: [Actual] ✅/❌/🎉
- [Metric 2]: [Actual] ✅/❌/🎉

## What Worked

1. [What performed better than expected]
2. [What users responded positively to]

**Why**: [Analysis of what caused success]

## What Didn't Work

1. [What missed targets]
2. [What users complained about]

**Why**: [Honest analysis of what went wrong]

## User Feedback

**Positive**:
- "[User quote]"

**Negative**:
- "[User quote or complaint]"

**Patterns**: [Common reactions]

## Unexpected Learnings

[What surprised us? What assumptions were challenged?]

## Recommendation: [Iterate / Expand / Pivot / Sunset]

**Reasoning**: [Why this recommendation based on data]

**Next Steps**:
1. [Concrete action]
2. [Concrete action]

**Metrics to Track (Next 30 Days)**:
- [Metric to validate recommendation]

## What We Learned

**Do More Of**:
- [Practice that worked]

**Do Less Of**:
- [Practice that didn't work]

**Assumptions Validated**: [What proved true]
**Assumptions Invalidated**: [What proved false]
```

## Notes

- **Iterate**: Met goals, room for improvement
- **Expand**: Exceeded goals, leverage success
- **Pivot**: Missed goals but learned something valuable
- **Sunset**: Missed goals, no path forward, free resources
