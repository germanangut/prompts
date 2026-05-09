---
title: "Workflow Design"
description: "Design a complete automated workflow for a business or technical process"
category: automation
type: prompt
tags: [workflow, automation, process-design, bpmn]
project_types: [automation, web-development, devops]
agent_capabilities: [automation, planning, workflow-design]
use_when: "When you need to design a new automated workflow or automate an existing manual process"
version: "1.0"
---

# Workflow Design

## Purpose

Use this prompt to design a complete automated workflow from a process description. Output includes a step-by-step workflow, trigger conditions, decision logic, integrations needed, and an implementation plan.

## Prompt

```
You are an automation architect. Design a complete automated workflow for the following process.

**Process to automate:** {{PROCESS_DESCRIPTION}}
**Current state (manual steps):**
{{CURRENT_STATE}}
**Desired outcome:** {{DESIRED_OUTCOME}}
**Tools / platforms available:** {{TOOLS}}
**Constraints:** {{CONSTRAINTS}}

**Design the workflow with these components:**

1. **Trigger**
   - What starts the workflow? (schedule, event, webhook, manual trigger, condition)
   - Trigger specification: timing, event type, filter conditions

2. **Input / Data Sources**
   - What data does the workflow consume?
   - Source systems, APIs, or files
   - Data validation rules

3. **Workflow Steps** (numbered)
   For each step:
   - Step name and description
   - Tool / service used
   - Input → Output
   - Error handling and retry logic
   - Estimated execution time

4. **Decision Points**
   - Where does the workflow branch?
   - Conditions for each branch
   - Default / fallback path

5. **Integrations**
   - External services and APIs required
   - Authentication method for each
   - Rate limits or quotas to consider

6. **Output / Notifications**
   - What does the workflow produce?
   - Who is notified, how, and when?
   - Success and failure notifications

7. **Error Handling and Recovery**
   - How are failures detected?
   - Retry strategy (attempts, backoff)
   - Manual intervention triggers
   - Dead letter / error queue

8. **Implementation Plan**
   - Recommended tool to build this (n8n, Zapier, Airflow, custom script, etc.)
   - Phase 1 (MVP): minimal viable automation
   - Phase 2: enhancements and edge case handling
   - Testing approach

9. **Workflow Diagram (text form)**
   Represent the workflow as an ASCII flowchart.
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{PROCESS_DESCRIPTION}}` | What process to automate | `When a new lead is created in Salesforce, enrich it with Clearbit, score it, and assign it to the right sales rep` |
| `{{CURRENT_STATE}}` | How it's done manually today | `Sales ops checks new leads daily, manually looks up LinkedIn, scores in a spreadsheet, emails the rep` |
| `{{DESIRED_OUTCOME}}` | What the automation should achieve | `Leads are enriched and assigned within 5 minutes of creation, with no manual work` |
| `{{TOOLS}}` | Platforms or tools available | `n8n, Salesforce API, Clearbit API, Slack, Google Sheets` |
| `{{CONSTRAINTS}}` | Budget, tech, or time constraints | `Must use existing tools, no new SaaS subscriptions, < 2 weeks to build` |

## Usage Notes

- Start with the MVP scope (Phase 1) and validate before adding complexity.
- Map error handling carefully — unhandled errors in automation can cause silent data loss.
- Document the workflow in a runbook so humans can take over if the automation fails.
