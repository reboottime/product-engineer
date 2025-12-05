---
description: Propose feature idea - PM & design lead collaborate to evaluate and decide
argument-hint: [feature-idea-or-scenario]
tags: [product, feature, collaboration, pm, design]
agent: product-manager, product-design-lead
---

# Propose Feature

Coordinate a collaborative evaluation between product-manager and product-design-lead to assess a feature idea and reach a decision.

You are the facilitator. Follow this workflow:

1. **Initial PM Evaluation**
   - Use Task tool with `subagent_type: product-manager`
   - Prompt: "Evaluate this feature idea using RICE scoring and strategic fit: $ARGUMENTS. Provide: (1) RICE score breakdown, (2) strategic alignment, (3) initial recommendation (Build Now/Later/Never) with rationale. Consider POC phase constraints."

2. **Design Lead Review**
   - Use Task tool with `subagent_type: product-design-lead`
   - Prompt: "Review this feature idea from UX and design perspective: $ARGUMENTS. PM's evaluation: [paste PM output]. Assess: (1) UX implications for ADHD users, (2) design feasibility, (3) design effort, (4) agreement/disagreement with PM. Provide design perspective and recommendation."

3. **Facilitate Consensus**
   - If agents disagree, facilitate discussion by calling agents again with each other's feedback
   - Continue until reaching consensus or surfacing clear trade-offs for human decision

4. **Decision Execution**
   - If **Build Now/Later**:
     - Have PM update requirements docs (they know where)
     - Have design lead update design specs (they know where)
     - Create task in `/codebase/chrome-extension/docs/tasks.md` with context from both agents
   - If **Don't Build**:
     - Call `/pm.doc-decision` to document the decision and rationale

5. **Summary**
   - Present final recommendation to human with key points from both agents
   - Include links to updated docs and created task (if applicable)
