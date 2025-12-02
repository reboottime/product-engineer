---
description: Create customer discovery interview guide with questions and probing techniques
tags: [product, discovery, pm, customer, research]
agent: product-manager
---

# Generate Discovery Questions

You are the product-manager agent. human is preparing for customer discovery interviews and needs an interview guide.

## Your Task

Create an interview guide with questions and probing techniques for customer discovery.

## Arguments

`[topic]` - Topic/problem area to explore

## Workflow

1. **Setup**:
   - If no `[topic]` argument: Ask human "What topic should I explore?"
   - Read `/Claude.md` (problem, solution, phase, principles)
   - Check current phase - if NOT "Customer Discovery": Ask if should proceed anyway

2. **Research problem space**:
   - WebSearch: `[topic] user problems`, `[topic] pain points`, `existing solutions [topic]`
   - Extract: common problems, pain points, existing solutions

3. **Ask human for context** using AskUserQuestion:
   - **Goal**: Problem validation / Solution exploration / Feature prioritization / Willingness to pay (multiSelect)
   - **Target User**: Current workaround users / Struggling / Gave up / Mixed group
   - **Hypotheses**: Yes, I have specific assumptions / No, open exploration

4. **Create interview guide**:
   - **Problem Validation** (5-7 questions): Does problem exist? How severe? How frequent?
   - **Solution Exploration** (5-7 questions): Ideal solution? Must-haves? Deal breakers?
   - **Prioritization** (3-5 questions): Willingness to pay? Urgency? Switching cost?
   - Add probing techniques for each section

5. **Write guide** at `/docs/product/research/discovery-guide-[topic].md`

6. **Verify**:
   - All three question types present
   - Questions are open-ended (not yes/no)
   - No leading questions
   - Probing tips included

## Output

`/docs/product/research/discovery-guide-[topic].md`

## Template

```markdown
# Customer Discovery Guide: [Topic]

**Date**: YYYY-MM-DD
**Goal**: [What we're trying to learn]
**Target Users**: [Who we're interviewing]

## Interview Protocol

- **Duration**: 30-45 minutes
- **Recording**: Ask permission
- **Note-taking**: Capture exact quotes
- **Follow-up**: Ask if you can reach out with clarifications

## Problem Validation Questions

**Goal**: Understand if problem exists, severity, frequency

1. [Open-ended question about problem experience]
2. [Question about frequency]
3. [Question about impact/severity]
4. [Question about current workarounds]
5. [Question about what makes it hard]
6. [Question about who else experiences this]
7. [Question about problem evolution]

**Probing Tips**:
- Ask "Tell me about the last time..." for specific examples
- Ask "Why?" 3-5 times to get to root causes
- Listen for: emotional language, frequency words, workarounds
- Avoid: leading questions, yes/no questions, solution pitches

## Solution Exploration Questions

**Goal**: Understand ideal solution and what features matter

1. [Question about ideal solution]
2. [Question about must-haves]
3. [Question about what wouldn't work]
4. [Question about integration/workflow]
5. [Question about tradeoffs]
6. [Question about what they don't need]

**Probing Tips**:
- Ask "Why?" to understand underlying needs
- Watch for body language (engagement vs disinterest)
- Note what they DON'T mention
- Avoid: presenting your solution, debating ideas

## Prioritization Questions

**Goal**: Understand urgency, willingness to pay, switching costs

1. [Question about budget/resources]
2. [Question about willingness to pay]
3. [Question about what they'd give up]
4. [Question about urgency]
5. [Question about alternatives]

**Probing Tips**:
- Ask about budget allocated to problem (reveals priority)
- Understand what they'd give up (reveals urgency)
- Let them suggest price first
- Avoid: pitching price, making promises

## Specific Hypotheses to Test

[If human provided hypotheses]

**Hypothesis**: [Statement to test]
- Test question: [Question to validate/invalidate]
- Confirms if: [Observable evidence]
- Disproves if: [Observable evidence]

## Interview Closing

1. "Is there anything I didn't ask that you think is important?"
2. "Do you know anyone else I should talk to?"
3. "Can I follow up if I have clarifying questions?"
4. "Would you like me to share what we build?"

## Post-Interview

- **Immediately**: Write raw notes (exact quotes, observations)
- **Within 24 hours**: Synthesize key insights
- **After 5-10 interviews**: Run `/pm.process-customer-research [notes-file]`
```

## Next Steps for human

1. Use this guide to interview 5-10 customers
2. Write notes in `docs/product/research/raw-notes-YYYY-MM-DD.md`
3. After 5+ interviews: `/pm.process-customer-research [notes-file]`
