---
title: "Technical Documentation Writer"
description: "Write clear technical documentation for a feature, API, or system"
category: writing
type: prompt
tags: [documentation, technical-writing, api-docs, developer-docs]
project_types: [web-development, data-science, devops]
agent_capabilities: [writing, documentation]
use_when: "When you need to create or update technical documentation for developers or technical users"
version: "1.0"
---

# Technical Documentation Writer

## Purpose

Use this prompt to generate well-structured technical documentation. Works for API references, feature guides, architecture overviews, runbooks, and more.

## Prompt

```
You are a senior technical writer. Write documentation for the following.

**What to document:** {{SUBJECT}}
**Documentation type:** {{DOC_TYPE}}
**Target audience:** {{AUDIENCE}}
**Technical context:**
{{TECHNICAL_CONTEXT}}

**Write the documentation following this structure:**

For an **API reference:**
- Overview (1 paragraph)
- Authentication
- Endpoints table (method, path, description)
- For each endpoint: description, request parameters, request body (with JSON schema), response schema, example request/response, error codes
- Rate limits and quotas

For a **Feature guide:**
- Overview
- Prerequisites
- Step-by-step instructions (numbered)
- Screenshots or diagram placeholders (mark as [SCREENSHOT: description])
- Common issues and solutions (FAQ format)

For an **Architecture overview:**
- Summary
- System diagram placeholder [DIAGRAM: description]
- Component descriptions
- Data flows
- Technology choices and rationale
- Scalability and failure considerations

For a **Runbook:**
- Purpose and scope
- Pre-conditions
- Step-by-step procedure (numbered, with exact commands)
- Expected outputs at each step
- Rollback procedure
- Escalation contacts

**Writing standards:**
- Use second person ("you") when addressing the reader.
- Use code blocks for all commands, code, and JSON.
- Use numbered lists for sequential steps, bullet lists for non-sequential items.
- Keep each section scannable — avoid walls of text.
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{SUBJECT}}` | What you are documenting | `The /users REST API`, `The caching feature`, `The deployment architecture` |
| `{{DOC_TYPE}}` | Type of documentation | `API reference`, `Feature guide`, `Architecture overview`, `Runbook` |
| `{{AUDIENCE}}` | Who will read this | `Backend developers`, `DevOps engineers`, `End users` |
| `{{TECHNICAL_CONTEXT}}` | Any code, specs, or notes about the subject | *(paste relevant code, OpenAPI spec, architecture notes, etc.)* |

## Usage Notes

- For API docs, paste the OpenAPI spec or function signatures into `{{TECHNICAL_CONTEXT}}`.
- Mark sections where screenshots are needed — add them manually after generating the text.
- Have a subject matter expert review for accuracy before publishing.
