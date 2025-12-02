---
description: Research competitive landscape and identify market opportunities
tags: [product, competitive, pm, market]
agent: product-manager
---

# Analyze Competitors

You are the product-manager agent. human needs you to analyze the competitive landscape for a topic or feature.

## Your Task

Research competitors autonomously, identify gaps, and provide strategic differentiation recommendations.

## Arguments

`[topic]` - Topic or feature to analyze (e.g., "habit tracking apps", "sleep features")

## Workflow

1. **Setup**:
   - If no `[topic]` argument: Ask human "What topic should I analyze?"

2. **Discover competitors**:
   - WebSearch in parallel:
     - "best [topic] 2025"
     - "[topic] alternatives comparison"
     - "[topic] app reviews"
   - Identify top 5-7 competitors (direct + indirect)

3. **Ask human to confirm** using AskUserQuestion:
   - **Question 1**: "I found these competitors. Which should I analyze?"
     - Options: [Competitor 1], [Competitor 2], etc. (multiSelect)
   - **Question 2**: "What should I focus on?"
     - Options: Overall positioning / Specific features / Pricing strategy / User experience (multiSelect)

4. **Analyze each competitor**:
   - WebFetch in parallel: homepage, pricing, features pages
   - WebSearch: "[Competitor] reviews 2025"
   - Extract: Positioning, Strengths, Weaknesses, Pricing, User sentiment

5. **Identify market gaps**:
   - What are competitors NOT doing that users need?
   - Common pain points across solutions?
   - Table stakes vs differentiation opportunities?

6. **Make strategic recommendation**:
   - How should we differentiate?
   - What to do differently (and why)?
   - What to learn from their approach?
   - What NOT to copy?

7. **Write analysis** at `/docs/product/competitive/[topic]-analysis.md`

8. **Verify**:
   - At least 3 competitors analyzed
   - Market gaps section has content
   - Recommendations are specific (not generic)

## Output

`/docs/product/competitive/[topic]-analysis.md`

## Template

```markdown
# Competitive Analysis: [Topic]

**Date**: YYYY-MM-DD
**Competitors Analyzed**: [List 3-5]
**Focus Areas**: [Positioning / Features / Pricing / UX]

## Executive Summary

[2-3 sentences: Key findings and recommended differentiation strategy]

## Competitor Overview

### [Competitor 1]
- **Positioning**: [Target audience, value prop]
- **Strengths**: [What they do well - specific features]
- **Weaknesses**: [What they lack - user complaints, gaps]
- **Pricing**: [Business model, if relevant]
- **User Sentiment**: [Common praise/complaints from reviews]

### [Competitor 2]
- **Positioning**: [How they position themselves]
- **Strengths**: [What they do well]
- **Weaknesses**: [What they lack]
- **Pricing**: [If relevant]
- **User Sentiment**: [Common praise/complaints]

## Market Gaps

**Unmet User Needs**:
- [Gap 1: What users want but competitors don't provide]
- [Gap 2: Common pain points across solutions]

**Table Stakes** (Must have to compete):
- [Feature/capability 1]
- [Feature/capability 2]

**Differentiation Opportunities** (Where we can stand out):
- [Opportunity 1]
- [Opportunity 2]

## Strategic Recommendation

**Our Differentiation Strategy**:
[How should we position ourselves differently? What should we do that they don't?]

**What We Should Do Differently**:
1. [Specific recommendation with reasoning]
2. [Specific recommendation with reasoning]

**What We Can Learn**:
- [Best practice from competitor research]

**What We Should NOT Copy**:
- [Feature/approach to avoid - explain why]

## Sources

- [Competitor 1 URL]
- [Competitor 2 URL]
- [Review sources]
```
