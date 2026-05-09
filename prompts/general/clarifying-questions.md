---
title: "Clarifying Questions Generator"
description: "Generate the right clarifying questions before starting any task"
category: general
type: prompt
tags: [clarification, requirements, discovery, questions]
agent_capabilities: [requirements-gathering, communication, planning]
use_when: "When a task or request is ambiguous and you need to gather the right information before starting work"
version: "1.0"
---

# Clarifying Questions Generator

## Purpose

Use this prompt before starting any complex task to identify exactly what information is missing. Asking the right questions upfront prevents wasted effort, rework, and misaligned deliverables.

## Prompt

```
You are a requirements analyst. Before any work begins on the following task, identify all the information needed to do it well.

**Task / Request:** {{TASK}}
**Requester context:** {{REQUESTER_CONTEXT}}
**What I already know:** {{KNOWN_INFORMATION}}

**Generate a structured list of clarifying questions:**

For each question:
- **Category:** (Purpose | Scope | Constraints | Format | Success Criteria | Technical | Timeline | Other)
- **Question:** The question itself, phrased simply and directly.
- **Why it matters:** One sentence explaining what decision this question informs.
- **Default assumption if not answered:** What you'll assume if the requester doesn't respond.

**Question categories to cover:**

1. **Purpose and Goals**
   - What is the ultimate objective? (Not just "what do you want" but "why do you want it?")
   - Who is the end user or beneficiary?
   - What does success look like?

2. **Scope**
   - What is explicitly IN scope?
   - What is OUT of scope?
   - Are there existing systems, documents, or work to build on?

3. **Constraints**
   - Budget? Timeline? Team size?
   - Technical constraints (language, platform, existing stack)?
   - Non-negotiable requirements?

4. **Format and Deliverables**
   - What format should the output be in?
   - How long / detailed should it be?
   - Who is the audience?

5. **Success Criteria**
   - How will the requester evaluate whether the output is good?
   - Are there examples of outputs they like?
   - What would make this output fail?

**Output format:**
Organize questions by category. Limit to the 10 most important questions — prioritize ruthlessly. Do not ask questions whose answers are obvious from the context.

**After listing questions, state:**
"If you can only answer 3 questions, make them: [1], [2], [3] — these are the most critical for getting the right output."
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{TASK}}` | The task or request that needs clarification | `Build a dashboard that shows our key metrics` |
| `{{REQUESTER_CONTEXT}}` | Who made the request and their role | `Head of Marketing at a 50-person SaaS company` |
| `{{KNOWN_INFORMATION}}` | What you already know | `They use Google Analytics and Salesforce; they want it web-based` |

## Usage Notes

- Use this prompt at the start of any new project or significant task.
- Share the generated questions with the requester and ask them to answer the top 3 first.
- If you can't get answers, use the default assumptions listed in the output and flag them clearly.
- Revisit this prompt when scope changes significantly during a project.
