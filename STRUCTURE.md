# Library Structure — Agent-Readable Map

This document describes every directory and file in the Prompts Master Library.
Autonomous agents should use `index.json` for programmatic access and this file
for human-readable orientation.

---

## Top-Level Layout

```
prompts/                   ← root of the library
├── README.md              ← human overview + navigation
├── STRUCTURE.md           ← this file
├── CONTRIBUTING.md        ← how to add prompts
├── index.json             ← machine-readable catalog (agent entry point)
│
├── prompts/               ← prompt files by category
│   ├── coding/
│   ├── writing/
│   ├── analysis/
│   ├── automation/
│   ├── agents/
│   └── general/
│
├── projects/              ← project-scoped prompt bundles
│   ├── web-development/
│   ├── data-science/
│   ├── automation/
│   ├── content-creation/
│   ├── mobile-app/
│   └── devops/
│
└── agents/                ← agent definitions and system-prompt templates
    ├── research/
    ├── coding/
    ├── planning/
    └── orchestrator/
```

---

## `prompts/` — Prompt Categories

| Directory | Purpose | Key Tags |
|---|---|---|
| `prompts/coding/` | Software engineering prompts | `code-generation`, `review`, `debugging`, `refactoring`, `testing` |
| `prompts/writing/` | Content and documentation prompts | `blog`, `docs`, `technical-writing`, `readme`, `report` |
| `prompts/analysis/` | Research, data, and reasoning prompts | `data-analysis`, `research`, `summarization`, `evaluation` |
| `prompts/automation/` | Automation design and scripting prompts | `workflow`, `script`, `pipeline`, `rpa`, `integration` |
| `prompts/agents/` | System prompts and meta-prompts for agents | `system-prompt`, `agent-config`, `multi-agent`, `role` |
| `prompts/general/` | Cross-domain general-purpose prompts | `brainstorm`, `planning`, `decision`, `qa` |

---

## `projects/` — Project Domains

| Directory | Purpose | Typical Prompts Inside |
|---|---|---|
| `projects/web-development/` | Web app projects | Architecture planning, component generation, API design |
| `projects/data-science/` | Data science projects | EDA, model selection, pipeline design, evaluation |
| `projects/automation/` | Automation projects | Workflow design, bot scripts, integration specs |
| `projects/content-creation/` | Content projects | Editorial planning, copywriting, SEO strategy |
| `projects/mobile-app/` | Mobile development | App architecture, UI flows, store listing copy |
| `projects/devops/` | DevOps projects | CI/CD pipelines, infra-as-code, incident runbooks |

---

## `agents/` — Agent Templates

| Directory | Agent Type | Capabilities |
|---|---|---|
| `agents/research/` | Research agent | Web search, summarization, citation, fact-checking |
| `agents/coding/` | Coding agent | Code generation, review, testing, refactoring |
| `agents/planning/` | Planning agent | Task decomposition, scheduling, prioritization |
| `agents/orchestrator/` | Orchestrator agent | Routing tasks to specialist agents, workflow management |

---

## Prompt File Format

Every prompt file uses this structure:

```markdown
---
title: "Short descriptive title"
description: "One-sentence description of what this prompt does"
category: coding | writing | analysis | automation | agents | general
type: prompt | template | system-prompt
tags: [tag1, tag2, tag3]
project_types: [web-development, data-science, ...]   # optional
agent_capabilities: [code-generation, analysis, ...]  # optional
use_when: "Plain English description of when to use this prompt"
version: "1.0"
---

# Title

## Purpose
...

## Prompt

\```
<the actual prompt text here>
\```

## Variables
| Variable | Description | Example |
|---|---|---|
| `{{VAR}}` | What it represents | example value |

## Usage Notes
...

## Example Output
...
```

---

## `index.json` Schema

```json
{
  "version": "1.0",
  "updated": "YYYY-MM-DD",
  "entries": [
    {
      "id": "unique-kebab-case-id",
      "title": "Human-readable title",
      "description": "One-sentence description",
      "file": "relative/path/to/file.md",
      "category": "coding",
      "type": "prompt",
      "tags": ["tag1", "tag2"],
      "project_types": ["web-development"],
      "agent_capabilities": ["code-generation"],
      "use_when": "Plain English trigger condition"
    }
  ]
}
```
