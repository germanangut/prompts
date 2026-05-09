---
title: "Debugging Assistant"
description: "Diagnose the root cause of a bug and suggest a fix"
category: coding
type: prompt
tags: [debugging, bug-fix, troubleshooting]
agent_capabilities: [debugging, analysis]
use_when: "When you have a bug, error, or unexpected behavior and need to identify the root cause and fix"
version: "1.0"
---

# Debugging Assistant

## Purpose

Use this prompt to systematically diagnose a bug. The model will reason through possible causes, identify the most likely root cause, and suggest a concrete fix with an explanation.

## Prompt

```
You are an expert debugger. Help me diagnose and fix the following issue.

**Language / Runtime:** {{LANGUAGE}}
**Framework / Library:** {{FRAMEWORK}}

**Problem Description:**
{{PROBLEM_DESCRIPTION}}

**Error Message / Stack Trace:**
\`\`\`
{{ERROR_MESSAGE}}
\`\`\`

**Relevant Code:**
\`\`\`{{LANGUAGE}}
{{CODE}}
\`\`\`

**What I expected to happen:**
{{EXPECTED_BEHAVIOR}}

**What actually happened:**
{{ACTUAL_BEHAVIOR}}

**Things I have already tried:**
{{ALREADY_TRIED}}

**Debugging steps:**
1. Analyze the error message and stack trace for direct clues.
2. Examine the relevant code for logical errors, incorrect assumptions, or edge cases.
3. List the 3 most likely root causes, ranked by probability.
4. For the most likely cause, provide:
   a. A clear explanation of why this causes the bug.
   b. The corrected code snippet.
   c. How to verify the fix works.
5. Note any secondary issues you spotted that may cause problems later.
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{LANGUAGE}}` | Programming language | `Python 3.11`, `TypeScript` |
| `{{FRAMEWORK}}` | Framework or library in use | `FastAPI`, `React 18`, `none` |
| `{{PROBLEM_DESCRIPTION}}` | Plain-language description of the problem | `API returns 500 when uploading files > 1MB` |
| `{{ERROR_MESSAGE}}` | Full error message or stack trace | *(paste the full error here)* |
| `{{CODE}}` | The code where the bug likely lives | *(paste relevant code)* |
| `{{EXPECTED_BEHAVIOR}}` | What should happen | `File is uploaded and stored in S3` |
| `{{ACTUAL_BEHAVIOR}}` | What actually happens | `Server crashes with MemoryError` |
| `{{ALREADY_TRIED}}` | Fixes you've already attempted | `Increased timeout, checked S3 permissions` |

## Usage Notes

- Always include the full stack trace — partial traces make diagnosis much harder.
- If you don't have a stack trace, describe the exact sequence of events that leads to the bug.
- The "already tried" field prevents the model from suggesting things you've already ruled out.
