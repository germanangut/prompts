---
title: "API Integration"
description: "Plan and implement an integration between two systems via API"
category: automation
type: prompt
tags: [api, integration, rest, webhook, automation]
project_types: [web-development, automation]
agent_capabilities: [code-generation, automation, integration]
use_when: "When you need to connect two systems or services via their APIs"
version: "1.0"
---

# API Integration

## Purpose

Use this prompt to plan and implement an API integration between two systems. Output covers the integration architecture, authentication, data mapping, error handling, and the implementation code.

## Prompt

```
You are an integration engineer. Help me design and implement an API integration.

**System A (Source):** {{SYSTEM_A}}
**System B (Destination):** {{SYSTEM_B}}
**Integration Goal:** {{GOAL}}
**Trigger:** {{TRIGGER}}
**Data to sync:** {{DATA_DESCRIPTION}}
**Language / Framework:** {{LANGUAGE}}
**Available credentials / auth:** {{AUTH_INFO}}

**Deliver:**

1. **Integration Architecture**
   - Pattern: webhook push | polling | event-driven | bidirectional sync
   - Recommended pattern with rationale
   - Flow diagram (text form): A → [trigger] → [transform] → [B]

2. **Authentication Plan**
   - Auth method for System A
   - Auth method for System B
   - How to store credentials securely (env vars, secrets manager)
   - Token refresh strategy (if OAuth)

3. **Data Mapping**
   | System A Field | Type | System B Field | Type | Transformation |
   |---|---|---|---|---|
   
   Note any required transformations, lookups, or enrichments.

4. **Implementation Code**
   Complete, runnable {{LANGUAGE}} code including:
   - API client setup with retry logic and timeout handling
   - Data fetching from System A
   - Data transformation
   - Data writing to System B
   - Idempotency (safe to run multiple times — use external IDs or checksums)
   - Logging of every API call (method, URL, status, duration)

5. **Error Handling Matrix**
   | Error Scenario | Detection | Response | Recovery |
   |---|---|---|---|

6. **Testing Plan**
   - How to test without affecting production data
   - Key test scenarios
   - How to mock the external APIs for unit tests

7. **Deployment and Monitoring**
   - How to deploy (cron, Lambda, container, workflow tool)
   - Key metrics to monitor
   - Alerting thresholds
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{SYSTEM_A}}` | Source system name and API type | `Salesforce (REST API)`, `Stripe (Webhooks)` |
| `{{SYSTEM_B}}` | Destination system name and API type | `HubSpot (REST API)`, `PostgreSQL (direct connection)` |
| `{{GOAL}}` | What the integration achieves | `When a deal is closed-won in Salesforce, create a project in Asana and notify Slack` |
| `{{TRIGGER}}` | What initiates the integration | `Salesforce webhook on opportunity stage change`, `Cron every 15 minutes` |
| `{{DATA_DESCRIPTION}}` | What data flows from A to B | `Opportunity name, value, owner email, close date → Project name, budget, assignee, due date` |
| `{{LANGUAGE}}` | Implementation language | `Python`, `Node.js` |
| `{{AUTH_INFO}}` | Auth type and any known details | `Salesforce: OAuth 2.0 JWT bearer; HubSpot: private app token` |

## Usage Notes

- Always test integrations in sandbox/staging environments first.
- Build idempotency from the start — APIs go down and messages get replayed.
- Log every API call — you will need these logs to debug issues in production.
