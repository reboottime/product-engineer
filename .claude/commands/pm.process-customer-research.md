---
description: Synthesize customer interviews/feedback into actionable insights
tags: [product, research, pm, customer]
agent: product-manager
---

# Process Customer Research

You are the product-manager agent. human has conducted customer interviews and needs you to synthesize insights.

## Your Task

Turn raw customer research into actionable insights, patterns, and recommendations.

## Arguments

`[file]` - Path to interview notes/transcripts

## Workflow

1. **Validate input**:
   - If no `[file]` argument: Use Glob `docs/product/research/raw-*.md`, ask human which one
   - Try Read the file to verify it exists and has content
   - If empty: Ask human if correct path

2. **Gather context**:
   - Read the research file
   - Read `/Claude.md` (product context)

3. **Ask human for context** using AskUserQuestion (if not clear from file):
   - **Goal**: Problem validation / Solution exploration / Willingness to pay / User behavior (multiSelect)
   - **Sample Size**: 1-3 / 4-7 / 8-10 / 10+ users

4. **Identify patterns**:
   - Themes that repeat across users
   - Pain points frequency
   - Severity indicators (emotional language, workarounds, willingness to pay)
   - Current solutions and why they don't work
   - What's NOT mentioned

5. **Extract key insights** (3-5 most important):
   - **Insight**: Clear statement (1 sentence)
   - **Evidence**: Direct quotes (3-5 quotes)
   - **Frequency**: N of M users mentioned
   - **Implication**: What this means for product

6. **Recommend actions**:
   - Features to validate: `/pm.validate-feature [feature-name]`
   - Problems to solve first (by frequency + severity)
   - Follow-up questions needed
   - Assumptions to test

7. **Write research summary** at `/docs/product/research/[date]-[topic]-insights.md`

8. **Verify**:
   - 3-5 key insights present
   - Each insight has quotes (evidence)
   - Frequency counts included
   - Recommended actions are specific

## Output

`/docs/product/research/[date]-[topic]-insights.md`

## Template

```markdown
# Customer Research Insights: [Topic]

**Date**: YYYY-MM-DD
**Source**: [Interviews / Feedback / Survey]
**Sample**: [N users, description]
**Goal**: [What we were trying to learn]

## Executive Summary

[2-3 sentences: Most important findings and implications]

## Key Insights

### 1. [Insight Title]

**Insight**: [1 sentence statement]

**Evidence**:
- "[Quote]" - User A
- "[Quote]" - User B
- "[Quote]" - User C

**Frequency**: [X of Y users]
**Implication**: [What this means for product]

---

### 2. [Insight Title]

**Insight**: [1 sentence statement]

**Evidence**:
- "[Quote]"
- "[Quote]"

**Frequency**: [X of Y users]
**Implication**: [What this means]

---

[Continue for 3-5 total insights]

## Patterns

**Problem Patterns**:
- [Pattern across users]

**Solution Patterns**:
- [Current workarounds]
- [What they wish existed]

**What We Didn't Hear**:
- [Expected topics users didn't mention]
- [Assumptions challenged]

## Recommended Actions

**High Priority** (Do next):
1. [Specific action - e.g., "/pm.validate-feature X"]
2. [Specific action - e.g., "Solve problem Y - 8/10 users mentioned"]

**Follow-Up Questions**:
- [Question to explore in next interviews]
- [Hypothesis to test]

## Next Steps

- [ ] [Immediate action]
- [ ] [Next action]
```

## Notes

- Look for patterns (n=1 is anecdote, n=5+ is pattern)
- Weight by frequency AND severity (common + painful = high priority)
- Use actual quotes as evidence
- Be honest about what you didn't hear
- Behavior > intentions
