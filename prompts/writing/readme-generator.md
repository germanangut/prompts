---
title: "README Generator"
description: "Generate a comprehensive README for any software project"
category: writing
type: prompt
tags: [readme, documentation, open-source, github]
project_types: [web-development, data-science, mobile-app, devops]
agent_capabilities: [writing, documentation]
use_when: "When you need to create or improve a README for a software project or repository"
version: "1.0"
---

# README Generator

## Purpose

Use this prompt to generate a professional, comprehensive README file for any software project. The output follows open-source best practices and includes all the sections developers expect.

## Prompt

```
You are a technical writer specializing in open-source documentation. Generate a complete README.md for the following project.

**Project Name:** {{PROJECT_NAME}}
**One-line description:** {{DESCRIPTION}}
**Tech stack:** {{TECH_STACK}}
**Project type:** {{PROJECT_TYPE}}
**Target users:** {{TARGET_USERS}}
**Key features:**
{{KEY_FEATURES}}
**Installation / setup notes:**
{{SETUP_NOTES}}
**License:** {{LICENSE}}

**Generate a README with these sections:**

1. **Header** — Project name, one-line description, badges (build status, license, version — use placeholders).
2. **Overview** — 2–3 sentences on what the project does and why it exists.
3. **Features** — Bullet list of key features.
4. **Demo** — Placeholder for screenshot or GIF: `![Demo](./docs/demo.gif)`.
5. **Prerequisites** — What needs to be installed before setup.
6. **Installation** — Step-by-step setup instructions with code blocks.
7. **Usage** — Basic usage examples with code blocks.
8. **Configuration** — Environment variables or config file options in a table.
9. **API Reference** (if applicable) — Key endpoints or functions.
10. **Contributing** — How to contribute (link to CONTRIBUTING.md if it exists).
11. **License** — License statement.
12. **Acknowledgements** (optional) — Credits to libraries or contributors.

**Formatting rules:**
- Use standard Markdown.
- All code examples in fenced code blocks with language specified.
- Keep it concise — developers skim READMEs.
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{PROJECT_NAME}}` | Name of the project | `DataFlow`, `AuthKit` |
| `{{DESCRIPTION}}` | One-line project description | `A lightweight Python library for streaming data pipelines` |
| `{{TECH_STACK}}` | Languages and frameworks used | `Python 3.11, FastAPI, PostgreSQL, Docker` |
| `{{PROJECT_TYPE}}` | Type of project | `CLI tool`, `REST API`, `Web app`, `Library`, `ML model` |
| `{{TARGET_USERS}}` | Who will use this | `Data engineers`, `Frontend developers`, `DevOps teams` |
| `{{KEY_FEATURES}}` | Bullet list of main features | `- Real-time streaming\n- Auto-retry on failure\n- Pluggable transforms` |
| `{{SETUP_NOTES}}` | Any specific setup requirements | `Requires Redis 7+; set REDIS_URL env var` |
| `{{LICENSE}}` | Software license | `MIT`, `Apache 2.0`, `GPL-3.0` |

## Usage Notes

- Fill in `{{SETUP_NOTES}}` with actual commands you use to set up the project locally.
- Replace badge placeholders with real badge URLs from shields.io after generation.
- Add real screenshots to the Demo section.
