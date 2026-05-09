---
title: "Compare Options"
description: "Systematically compare and evaluate a set of options against defined criteria"
category: analysis
type: prompt
tags: [comparison, evaluation, decision-support, scoring]
agent_capabilities: [analysis, evaluation, decision-support]
use_when: "When you need to choose between multiple options and want a structured, objective comparison"
version: "1.0"
---

# Compare Options

## Purpose

Use this prompt to get a structured, criteria-based comparison of multiple options. Useful for technology selection, vendor evaluation, architecture decisions, hiring decisions, and any multi-option choice.

## Prompt

```
You are a strategic analyst. Help me evaluate and compare the following options.

**Decision to make:** {{DECISION}}
**Options to compare:**
{{OPTIONS}}

**Evaluation Criteria:**
{{CRITERIA}}

**Constraints:**
{{CONSTRAINTS}}

**Context:**
{{CONTEXT}}

**Comparison process:**

1. **Criteria Weighting**
   Assign a weight (1–5) to each criterion based on its importance to {{DECISION}}. Explain each weight.

2. **Scoring Matrix**
   Build a table: rows = options, columns = criteria.
   Score each option on each criterion from 1 (poor) to 5 (excellent).
   Include a weighted total score column.

   | Option | Criterion 1 (wt) | Criterion 2 (wt) | ... | Weighted Total |
   |---|---|---|---|---|

3. **Narrative Analysis**
   For each option, write 2–3 sentences on:
   - Its strongest advantage
   - Its biggest weakness or risk
   - Best fit scenario (when would you choose this option?)

4. **Recommendation**
   - Primary recommendation with rationale
   - Conditions under which the recommendation would change
   - Runner-up option and why

5. **Risk Assessment**
   - Top 2 risks with the recommended option and how to mitigate them

6. **Open Questions**
   - Any information gaps that, if resolved, might change the recommendation
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{DECISION}}` | The decision to be made | `Which database to use for our real-time analytics system` |
| `{{OPTIONS}}` | List of options to compare | `ClickHouse, BigQuery, Snowflake, DuckDB` |
| `{{CRITERIA}}` | Evaluation criteria | `Query performance, cost, operational overhead, team familiarity, scalability` |
| `{{CONSTRAINTS}}` | Hard constraints that options must meet | `Must be < $5k/month, must support SQL, must be self-hostable` |
| `{{CONTEXT}}` | Background on the situation | `We have a 10-person team, 500GB data, expect 10x growth in 18 months` |

## Usage Notes

- Define criteria before you see the options — this prevents anchoring bias.
- Add weights that reflect your real priorities; the weighted total drives the recommendation.
- Treat the recommendation as input to your decision, not the final word.
