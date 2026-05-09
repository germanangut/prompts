# Contributing to the Prompts Library

Thank you for contributing! This guide explains how to add new prompts, templates, or agent definitions to the library in a way that keeps it consistent and agent-readable.

---

## Before You Start

- Check `index.json` and the relevant category `README.md` to ensure the prompt doesn't already exist.
- Choose the correct category for your prompt (see [STRUCTURE.md](./STRUCTURE.md)).
- Use an existing prompt file as a reference for formatting.

---

## Adding a Prompt

### 1. Create the file

Place your file in the appropriate directory:

```
prompts/<category>/<descriptive-kebab-case-name>.md
```

Examples:
- `prompts/coding/generate-rest-api.md`
- `prompts/writing/blog-post-outline.md`
- `projects/web-development/tech-stack-selection.md`

### 2. Add YAML front-matter

Every prompt file **must** begin with YAML front-matter:

```markdown
---
title: "Short descriptive title"
description: "One-sentence description of what this prompt does"
category: coding | writing | analysis | automation | agents | general
type: prompt | template | system-prompt
tags: [tag1, tag2, tag3]
project_types: [web-development, data-science, automation, content-creation, mobile-app, devops]
agent_capabilities: [code-generation, analysis, summarization, planning, research, automation]
use_when: "Plain English description of when to use this prompt"
version: "1.0"
---
```

Required fields: `title`, `description`, `category`, `type`, `tags`, `use_when`, `version`
Optional fields: `project_types`, `agent_capabilities`

### 3. Write the prompt body

Follow this structure:

```markdown
# Title

## Purpose
One paragraph explaining what this prompt is for and why it's useful.

## Prompt

\```
<the actual prompt text — use {{VARIABLE}} for placeholders>
\```

## Variables
| Variable | Description | Example |
|---|---|---|
| `{{VARIABLE}}` | What it represents | example value |

## Usage Notes
- Any tips, caveats, or best practices for using this prompt.

## Example Output
Optional: a short example of what a good response looks like.
```

### 4. Update `index.json`

Add a new entry to the `entries` array in `index.json`:

```json
{
  "id": "unique-kebab-case-id",
  "title": "Human-readable title",
  "description": "One-sentence description",
  "file": "prompts/coding/your-file.md",
  "category": "coding",
  "type": "prompt",
  "tags": ["tag1", "tag2"],
  "project_types": ["web-development"],
  "agent_capabilities": ["code-generation"],
  "use_when": "When you need to..."
}
```

---

## Naming Conventions

| Thing | Convention | Example |
|---|---|---|
| File names | `kebab-case.md` | `generate-rest-api.md` |
| Prompt IDs in index.json | `kebab-case` unique across the library | `coding-generate-rest-api` |
| Variable placeholders | `{{UPPER_SNAKE_CASE}}` | `{{PROJECT_NAME}}` |
| Tags | `kebab-case` | `code-generation` |

---

## Categories Reference

| Category | Directory | Use for |
|---|---|---|
| `coding` | `prompts/coding/` | Software engineering tasks |
| `writing` | `prompts/writing/` | Content and documentation |
| `analysis` | `prompts/analysis/` | Research, data, and reasoning |
| `automation` | `prompts/automation/` | Workflows, scripts, pipelines |
| `agents` | `prompts/agents/` | AI agent system prompts |
| `general` | `prompts/general/` | Cross-domain prompts |

---

## Quality Checklist

Before submitting:

- [ ] YAML front-matter is present and all required fields are filled
- [ ] Prompt uses `{{VARIABLE}}` syntax for all dynamic parts
- [ ] Variables are documented in a table
- [ ] `index.json` has a new entry for the prompt
- [ ] File is placed in the correct category directory
- [ ] File name is `kebab-case.md`
- [ ] The prompt has been tested and produces useful output
