---
title: "Agent Self-Reflection"
description: "Prompt an agent to evaluate, critique, and improve its own output"
category: agents
type: prompt
tags: [self-reflection, evaluation, quality, improvement, agent]
agent_capabilities: [evaluation, self-improvement, quality-assurance]
use_when: "When you want an agent to critically review its own output before delivering it, improving accuracy and quality"
version: "1.0"
---

# Agent Self-Reflection

## Purpose

Use this prompt to add a self-reflection step to any agent workflow. After the agent produces an initial output, this prompt asks it to critically evaluate that output and produce an improved version. This pattern significantly reduces errors and improves output quality.

## Prompt

```
You previously generated the following output in response to a task. Now critically evaluate it.

**Original Task:**
{{ORIGINAL_TASK}}

**Your Previous Output:**
{{PREVIOUS_OUTPUT}}

**Self-Reflection Criteria:**
Evaluate your output against these dimensions:

1. **Correctness** — Are there any factual errors, logical flaws, or incorrect assumptions?
   Score: 1–5 | Issues found: [list]

2. **Completeness** — Does the output fully address the original task? What is missing?
   Score: 1–5 | Gaps found: [list]

3. **Clarity** — Is the output clear, well-organized, and easy to understand?
   Score: 1–5 | Clarity issues: [list]

4. **Relevance** — Is everything in the output relevant to the task? Is there unnecessary filler?
   Score: 1–5 | Irrelevant content: [list]

5. **{{DOMAIN_SPECIFIC_CRITERION}}** — {{DOMAIN_CRITERION_DESCRIPTION}}
   Score: 1–5 | Issues found: [list]

**Reflection Summary:**
- Overall Quality Score: [average of above] / 5
- Top 3 issues to fix: [ranked list]
- What I would do differently: [brief explanation]

**Improved Output:**
Now produce an improved version that addresses all identified issues. Clearly mark changes with [IMPROVED] tags if comparing against the original, or simply rewrite the full output if it's easier.

**Confidence Statement:**
After improvement, state: "I am [X]% confident this output fully and correctly addresses the original task because [reason]. The remaining [100-X]% uncertainty is due to [specific unknowns]."
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{ORIGINAL_TASK}}` | The task that was originally given | `Write a Python function that parses a CSV file and returns a list of dicts` |
| `{{PREVIOUS_OUTPUT}}` | The agent's first attempt at the task | *(paste the output to be reviewed)* |
| `{{DOMAIN_SPECIFIC_CRITERION}}` | A criterion specific to the domain | `Security` (for code), `Accuracy` (for research), `Tone` (for writing) |
| `{{DOMAIN_CRITERION_DESCRIPTION}}` | What this criterion means | `Does the code avoid common security vulnerabilities?` |

## Usage Notes

- Use this as a second pass in any high-stakes workflow — the improvement is consistently significant.
- For coding tasks, set `{{DOMAIN_SPECIFIC_CRITERION}}` to "Security" or "Performance".
- For writing tasks, set it to "Tone and Voice" or "SEO Optimization".
- You can chain multiple self-reflection passes, but two passes usually captures most improvements.
