# Agent Description Best Practices

**Date:** 2025-12-01
**Source:** Claude Code official documentation

## Key Principle

Agent descriptions control automatic delegation. They tell Claude when to invoke an agent based on task context.

## Description Pattern

**Structure:** `[What it does] + [When to use - with keywords] + [Authority/Philosophy]`

## Two Valid Styles

### 1. Action-Oriented (Execution Agents)

**Use for:** Procedural tasks, specific workflows, tool execution

**Example:**
```
Use this agent to automatically commit changes, push to remote, create meaningful
commit messages following conventional commit standards, and manage git workflows.
```

**Best for:** release-manager, build-engineer, test-runner

### 2. Conceptual (Strategic Agents)

**Use for:** Decision-making, strategic planning, judgment calls

**Example:**
```
Makes product decisions, validates problems, prioritizes ruthlessly.
Use PROACTIVELY for feature validation, roadmap planning, prioritization.
Teaches product thinking through decision-making.
```

**Best for:** product-manager, tech-lead, compliance-manager

## Critical Elements

1. **Trigger keywords** - Terms users naturally mention (PDF, commit, feature, roadmap)
2. **Proactive phrases** - "Use PROACTIVELY", "MUST BE USED", "Use immediately after"
3. **Specific capabilities** - List concrete actions (validate, prioritize, commit, push)
4. **Context clues** - When/where to use it (git workflows, product decisions)

## Common Mistakes

❌ Too vague: "Helps with data"
❌ Missing triggers: No keywords for pattern matching
❌ Wrong style: Action-oriented for strategic agents or vice versa
❌ No "when": Only describes what, not when to invoke

## Recommended Format by Agent Type

**Execution Agents:**
```
Use this agent to [action verbs]. [Specific capabilities].
Essential for [keywords/triggers].
```

**Strategic Agents:**
```
[Authority statement]. Use PROACTIVELY for [triggers with keywords].
[Philosophy/approach].
```

## Examples from Our Setup

**Good - Landing Page Expert:**
```
Landing page optimization specialist for LivMate. Evaluates existing pages and designs
new high-converting landing pages for health/wellness apps using conversion psychology,
behavioral design, and health-specific messaging principles.
```
✅ Domain-specific, dual capabilities, strong keywords

**Good - Release Manager:**
```
Use this agent to automatically commit changes, push to remote, create meaningful
commit messages following conventional commit standards, and manage git workflows.
```
✅ Clear actions, specific capabilities, execution-focused

**Needs improvement - Product Manager:**
```
Makes product decisions, validates problems, prioritizes ruthlessly.
Teaches product thinking through decision-making.
```
⚠️ Good conceptual style, but missing trigger keywords for invocation
