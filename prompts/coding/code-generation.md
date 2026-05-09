---
title: "Code Generation"
description: "Generate well-structured, documented code from a plain-language description"
category: coding
type: prompt
tags: [code-generation, programming, boilerplate]
agent_capabilities: [code-generation]
use_when: "When you need to create new code from scratch based on a description or requirements"
version: "1.0"
---

# Code Generation

## Purpose

Use this prompt to generate clean, well-structured code in any programming language from a plain-language description of what you need. The output includes the code itself plus brief inline comments explaining key decisions.

## Prompt

```
You are an expert software engineer. Generate {{LANGUAGE}} code that accomplishes the following:

**Task Description:**
{{TASK_DESCRIPTION}}

**Requirements:**
{{REQUIREMENTS}}

**Constraints:**
- Language: {{LANGUAGE}}
- Framework/Library (if any): {{FRAMEWORK}}
- Style guide / conventions: {{STYLE_GUIDE}}

**Output format:**
1. The complete, runnable code with inline comments explaining non-obvious decisions.
2. A short explanation (3–5 sentences) of the approach you chose.
3. A list of any assumptions you made.
4. Any follow-up steps the developer should take (e.g., install dependencies, set env vars).

Do not include placeholder comments like "// TODO: implement this". Produce complete, working code.
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{LANGUAGE}}` | Programming language | `Python`, `TypeScript`, `Go` |
| `{{TASK_DESCRIPTION}}` | What the code should do | `Parse a CSV file and insert rows into a PostgreSQL table` |
| `{{REQUIREMENTS}}` | Specific requirements or acceptance criteria | `Handle errors gracefully; log failures; support batch inserts` |
| `{{FRAMEWORK}}` | Framework or library to use (use "none" if not applicable) | `FastAPI`, `Express`, `none` |
| `{{STYLE_GUIDE}}` | Coding style to follow | `PEP 8`, `Google style`, `Airbnb ESLint` |

## Usage Notes

- Be as specific as possible in `{{TASK_DESCRIPTION}}` — the more detail, the better the output.
- If you have an existing codebase, describe its patterns in `{{STYLE_GUIDE}}`.
- For complex tasks, break them into smaller sub-tasks and use this prompt per sub-task.

## Example Output

> **Approach:** I used Python's `csv` module to parse the file row by row and `psycopg2` with a connection pool for efficient batch inserts…
