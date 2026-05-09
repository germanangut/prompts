---
title: "Code Review"
description: "Review code for bugs, security issues, performance problems, and style violations"
category: coding
type: prompt
tags: [code-review, quality, security, best-practices]
agent_capabilities: [code-review, analysis]
use_when: "When you need a thorough review of existing code before merging or shipping"
version: "1.0"
---

# Code Review

## Purpose

Use this prompt to get a comprehensive, structured code review covering correctness, security, performance, readability, and maintainability. Output is organized by severity so the most critical issues are addressed first.

## Prompt

```
You are a senior software engineer performing a thorough code review. Review the following {{LANGUAGE}} code and provide structured feedback.

**Code to review:**
\`\`\`{{LANGUAGE}}
{{CODE}}
\`\`\`

**Context:**
- Purpose of this code: {{PURPOSE}}
- Target environment: {{ENVIRONMENT}}
- Known constraints: {{CONSTRAINTS}}

**Review the code across these dimensions and assign severity (Critical / High / Medium / Low / Info):**

1. **Correctness** — Logic errors, edge cases not handled, off-by-one errors.
2. **Security** — Injection vulnerabilities, insecure dependencies, exposed secrets, improper input validation.
3. **Performance** — Unnecessary computations, N+1 queries, memory leaks, blocking calls.
4. **Readability** — Naming, comments, function length, complexity.
5. **Maintainability** — Coupling, test coverage, error handling, logging.
6. **Best Practices** — Language/framework conventions, design patterns, SOLID principles.

**Output format:**
For each issue:
- **Severity:** Critical | High | Medium | Low | Info
- **Dimension:** (from the list above)
- **Location:** Line number or function name
- **Issue:** What is wrong
- **Suggestion:** How to fix it
- **Code example:** (if applicable) show the corrected snippet

End with a **Summary** section: overall assessment, top 3 priorities, and a confidence score (1–10) for the code being production-ready.
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{LANGUAGE}}` | Programming language of the code | `Python`, `JavaScript`, `Java` |
| `{{CODE}}` | The code to be reviewed | *(paste code here)* |
| `{{PURPOSE}}` | What this code does | `Handles user authentication via JWT` |
| `{{ENVIRONMENT}}` | Where it runs | `Node.js 20, AWS Lambda`, `Python 3.11, Docker` |
| `{{CONSTRAINTS}}` | Any known limitations or requirements | `Must process 10k req/sec`, `Legacy DB schema` |

## Usage Notes

- For large files, break the review into logical sections (e.g., per function or class).
- Always include the `{{PURPOSE}}` — it helps the reviewer understand intent vs. implementation.
- Critical and High severity issues should be resolved before merging.
