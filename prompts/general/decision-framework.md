---
title: "Decision Framework"
description: "Evaluate options systematically and make a well-reasoned decision"
category: general
type: prompt
tags: [decision, evaluation, framework, options-analysis]
agent_capabilities: [analysis, decision-support, evaluation]
use_when: "When you face a decision with multiple options and want a structured, bias-aware approach"
version: "1.0"
---

# Decision Framework

## Purpose

Use this prompt to make complex decisions in a structured, documented way. The output reduces cognitive bias, surfaces hidden trade-offs, and produces a clear recommendation with supporting rationale.

## Prompt

```
You are a decision analyst helping me make a well-reasoned decision.

**Decision to make:** {{DECISION}}
**Options under consideration:** {{OPTIONS}}
**Key stakeholders:** {{STAKEHOLDERS}}
**Timeline for the decision:** {{TIMELINE}}
**Reversibility:** {{REVERSIBILITY}}
**Context and background:** {{CONTEXT}}

**Decision Analysis Process:**

1. **Frame the Decision**
   - Restate the core question in one sentence.
   - What type of decision is this? (Strategic / Tactical / Operational / Irreversible)
   - What would a great outcome look like?
   - What would a bad outcome look like?

2. **Define Criteria**
   List the criteria that a good option must satisfy, weighted by importance:
   | Criterion | Weight (1–5) | Rationale |
   |---|---|---|
   
   Separate: Must-Have (knock-out criteria) vs. Nice-to-Have.

3. **Evaluate Options**
   For each option:
   - Does it pass all Must-Have criteria? (If not, eliminate it.)
   - Score it on each Nice-to-Have criterion (1–5).
   - Calculate weighted score.
   - Identify top 2 strengths and top 2 risks.

4. **Scoring Matrix**
   | Option | Criterion 1 (wt) | Criterion 2 (wt) | ... | Weighted Total |
   |---|---|---|---|---|

5. **Bias Check**
   Actively look for these cognitive biases in your reasoning:
   - Confirmation bias: Are you favoring evidence that supports your existing preference?
   - Anchoring: Are you over-weighting the first option considered?
   - Sunk cost: Are you factoring in past costs that are irrelevant to future outcomes?
   - Status quo bias: Are you avoiding change even when change is better?

6. **Pre-Mortem**
   Assume the recommended option was chosen and failed. What went wrong?
   List the 3 most likely failure modes.

7. **Recommendation**
   - Recommended option
   - Rationale (3–5 key reasons)
   - Key assumptions underlying this recommendation
   - Conditions that would change the recommendation
   - Implementation first step

8. **Decision Record**
   A brief (5-bullet) summary to document *why* this decision was made — for future reference.
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{DECISION}}` | What you need to decide | `Which cloud provider to use for our new infrastructure` |
| `{{OPTIONS}}` | Options on the table | `AWS, Google Cloud, Azure, DigitalOcean` |
| `{{STAKEHOLDERS}}` | Who is affected by and involved in this decision | `CTO, engineering team, finance team` |
| `{{TIMELINE}}` | When the decision must be made | `Must decide by end of this week` |
| `{{REVERSIBILITY}}` | How hard is it to change course later | `High — switching cloud providers is very costly and slow` |
| `{{CONTEXT}}` | Relevant background | `Growing startup, 5-person engineering team, tight budget, 2x growth expected next year` |

## Usage Notes

- Fill in criteria *before* you know which option you'll recommend — prevents post-rationalization.
- The Pre-Mortem step is the most valuable for high-stakes, hard-to-reverse decisions.
- Store the Decision Record somewhere accessible — you'll thank yourself when someone asks "why did we do this?" in 12 months.
