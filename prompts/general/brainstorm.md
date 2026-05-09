---
title: "Brainstorm"
description: "Generate a wide range of ideas on any topic using structured creative thinking"
category: general
type: prompt
tags: [brainstorm, ideation, creativity, problem-solving]
agent_capabilities: [ideation, creativity, planning]
use_when: "When you need to generate many diverse ideas on a topic before narrowing down"
version: "1.0"
---

# Brainstorm

## Purpose

Use this prompt to generate a rich set of ideas on any topic. The output uses multiple brainstorming techniques to ensure diversity — combining obvious ideas, wild ideas, and cross-domain analogies.

## Prompt

```
You are a creative thinking facilitator. Help me brainstorm ideas for the following challenge.

**Challenge / Question:** {{CHALLENGE}}
**Context:** {{CONTEXT}}
**Constraints:** {{CONSTRAINTS}}
**Desired quantity:** {{IDEA_COUNT}} ideas

**Use these techniques to generate diverse ideas:**

1. **Classic brainstorm** — Generate {{IDEA_COUNT}} ideas without judgment. Quantity over quality. Include obvious and non-obvious ideas.

2. **Reverse brainstorm** — List 5 ways to make the problem *worse*, then flip each into a positive solution.

3. **SCAMPER** — Apply each lens:
   - **S**ubstitute: What can be substituted in the current approach?
   - **C**ombine: What can be combined with something else?
   - **A**dapt: What can be adapted from another domain?
   - **M**odify / Magnify: What can be changed, enlarged, or emphasized?
   - **P**ut to other uses: Can the core idea be used differently?
   - **E**liminate: What can be removed to simplify?
   - **R**everse / Rearrange: What happens if you flip the sequence or structure?

4. **Analogies** — How do these fields solve a similar challenge? Apply one insight from each:
   - Nature / biology
   - Sports / games
   - Architecture / design
   - Completely unrelated industry: {{RANDOM_INDUSTRY}}

**Output format:**
1. Numbered list of all ideas (no explanations — just the idea, one line each).
2. Top 5 most promising ideas with a 2-sentence explanation of why each is interesting.
3. Wildest idea that might actually work — with brief rationale.
4. Recommended next step for the most promising idea.
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{CHALLENGE}}` | The problem or question to brainstorm | `How can we reduce customer churn for a SaaS product?` |
| `{{CONTEXT}}` | Background and current situation | `B2B SaaS, 500 customers, avg 5% monthly churn, main reason: poor onboarding` |
| `{{CONSTRAINTS}}` | What must be true for any idea | `Budget < $50k, must be implementable in 90 days, no major engineering work` |
| `{{IDEA_COUNT}}` | How many ideas to generate | `20`, `50` |
| `{{RANDOM_INDUSTRY}}` | An industry far from your own | `Aviation`, `Hospitality`, `Military` |

## Usage Notes

- Don't filter ideas during generation — the value is in volume and diversity.
- Hold a team session to dot-vote on the raw ideas before deep-diving on any one.
- The SCAMPER framework is especially useful when you feel like you've already thought of everything.
