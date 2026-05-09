---
title: "Root Cause Analysis"
description: "Perform a structured root cause analysis (RCA) on a problem or incident"
category: analysis
type: prompt
tags: [rca, root-cause, incident, problem-solving, 5-whys]
agent_capabilities: [analysis, reasoning, problem-solving]
use_when: "When a problem or incident has occurred and you need to identify the true underlying cause to prevent recurrence"
version: "1.0"
---

# Root Cause Analysis

## Purpose

Use this prompt to perform a rigorous root cause analysis (RCA) on any problem or incident. The output uses established RCA frameworks (5 Whys, Fishbone/Ishikawa) to find the true root cause — not just the proximate cause — and produce preventive recommendations.

## Prompt

```
You are an expert in root cause analysis and systems thinking. Perform a thorough RCA on the following problem.

**Problem Statement:** {{PROBLEM_STATEMENT}}
**When it occurred:** {{WHEN}}
**Impact:** {{IMPACT}}
**System / Process affected:** {{SYSTEM}}
**Timeline of events:**
{{TIMELINE}}
**Immediate actions already taken:** {{IMMEDIATE_ACTIONS}}

**RCA Process:**

1. **Problem Definition**
   - Restate the problem clearly and precisely.
   - Distinguish symptoms from the actual problem.
   - Define what "normal" looks like and how this deviated.

2. **5 Whys Analysis**
   Starting from the problem statement, ask "why did this happen?" five times, building a causal chain.
   - Why 1: [proximate cause]
   - Why 2: [contributing cause]
   - Why 3: [systemic cause]
   - Why 4: [process/culture cause]
   - Why 5: [root cause]

3. **Fishbone Diagram (Text Form)**
   Identify contributing factors across these categories:
   - **People:** human errors, skills, communication
   - **Process:** procedure gaps, workflow issues
   - **Technology:** system failures, bugs, infrastructure
   - **Environment:** external factors, conditions
   - **Materials/Data:** data quality, dependencies

4. **Root Cause Statement**
   A single clear sentence: "The root cause is [X] because [evidence]."

5. **Contributing Factors**
   List secondary factors that allowed the root cause to cause the problem.

6. **Corrective Actions**
   | Action | Type | Owner | Deadline |
   |---|---|---|---|
   | (immediate fix) | Containment | | |
   | (root cause fix) | Corrective | | |
   | (prevent recurrence) | Preventive | | |

7. **Lessons Learned**
   - What did this reveal about our system or process?
   - What early warning signs were missed?
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{PROBLEM_STATEMENT}}` | Clear description of what went wrong | `Production database went down for 45 minutes on 2024-11-15` |
| `{{WHEN}}` | Date, time, and duration | `2024-11-15 14:30 UTC, lasted 45 minutes` |
| `{{IMPACT}}` | Business and technical impact | `~2,000 users unable to log in; $40k estimated revenue loss` |
| `{{SYSTEM}}` | The system or process that failed | `User authentication service (PostgreSQL + Node.js)` |
| `{{TIMELINE}}` | Chronological events leading to and during the incident | `14:30 - Deploy; 14:35 - Alerts; 14:40 - DB CPU 100%...` |
| `{{IMMEDIATE_ACTIONS}}` | What was done to stop the bleeding | `Rolled back deployment at 15:15; DB restarted` |

## Usage Notes

- A good RCA takes time — gather as much timeline data as possible before starting.
- The 5 Whys works best for straightforward causal chains; use the Fishbone for complex systemic issues.
- Share the final RCA with all stakeholders and track corrective actions to completion.
