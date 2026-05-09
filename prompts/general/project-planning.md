---
title: "Project Planning"
description: "Create a structured project plan from a goal or brief"
category: general
type: prompt
tags: [planning, project-management, roadmap, milestones]
agent_capabilities: [planning, task-decomposition, project-management]
use_when: "When you have a goal or project idea and need a structured plan with milestones, tasks, and timeline"
version: "1.0"
---

# Project Planning

## Purpose

Use this prompt to turn a project goal or brief into a full project plan. Output includes objectives, milestones, task breakdown, risk assessment, and a timeline.

## Prompt

```
You are an experienced project manager. Create a structured project plan for the following.

**Project Name:** {{PROJECT_NAME}}
**Goal:** {{GOAL}}
**Scope:** {{SCOPE}}
**Team:** {{TEAM}}
**Budget:** {{BUDGET}}
**Deadline:** {{DEADLINE}}
**Key constraints or risks you already know about:** {{KNOWN_RISKS}}

**Create a complete project plan:**

1. **Project Charter (1 page summary)**
   - Problem statement
   - Solution approach
   - Success criteria (measurable)
   - Out of scope (explicit list)
   - Key stakeholders

2. **Milestones**
   List 3–6 major milestones with:
   - Milestone name
   - Description of what's complete at this point
   - Target date
   - Definition of done

3. **Work Breakdown Structure**
   For each milestone, list the tasks required:
   - Task name
   - Owner (role)
   - Estimated effort (hours or days)
   - Dependencies
   - Priority: Critical | High | Medium | Low

4. **Timeline**
   Present a text-based Gantt-style view:
   Week 1: [tasks]
   Week 2: [tasks]
   ...

5. **Risk Register**
   | Risk | Likelihood (H/M/L) | Impact (H/M/L) | Mitigation | Owner |
   |---|---|---|---|---|

6. **Resource Plan**
   - Roles needed and time commitment
   - External dependencies (vendors, APIs, approvals)
   - Budget breakdown by category

7. **Communication Plan**
   - Who gets what updates, how often, and in what format
   - Decision-making process and escalation path

8. **Open Questions**
   - What do we need to decide before work can begin?
   - Information gaps that could affect the plan
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{PROJECT_NAME}}` | Name of the project | `Customer Portal v2` |
| `{{GOAL}}` | What success looks like | `Launch a self-service customer portal that reduces support tickets by 30%` |
| `{{SCOPE}}` | What's included | `Web app, API, admin dashboard; no mobile app` |
| `{{TEAM}}` | Who is on the team | `2 engineers, 1 designer, 1 PM — all part-time (50%)` |
| `{{BUDGET}}` | Available budget | `$80,000 total` |
| `{{DEADLINE}}` | Target completion date | `2025-09-01` |
| `{{KNOWN_RISKS}}` | Pre-identified risks | `External API dependency with history of outages; design resource bottleneck` |

## Usage Notes

- Review the plan with the team before committing — estimates are rough and must be validated.
- The Risk Register is the most important section for projects with tight deadlines or budgets.
- Revisit the plan every 2 weeks and update milestones as you learn more.
