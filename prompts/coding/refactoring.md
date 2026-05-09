---
title: "Code Refactoring"
description: "Refactor existing code to improve readability, structure, and maintainability without changing behavior"
category: coding
type: prompt
tags: [refactoring, clean-code, maintainability, readability]
agent_capabilities: [code-generation, code-review]
use_when: "When you have working code that needs to be cleaned up, simplified, or restructured"
version: "1.0"
---

# Code Refactoring

## Purpose

Use this prompt to refactor existing, working code. The model will improve structure, naming, readability, and maintainability while preserving the original behavior. The output includes both the refactored code and an explanation of changes made.

## Prompt

```
You are an expert software engineer specializing in clean code and refactoring. Refactor the following {{LANGUAGE}} code.

**Original Code:**
\`\`\`{{LANGUAGE}}
{{ORIGINAL_CODE}}
\`\`\`

**Refactoring Goals:**
{{REFACTORING_GOALS}}

**Constraints (do NOT change these):**
- Public API / function signatures must remain the same: {{KEEP_API}}
- Must maintain compatibility with: {{COMPATIBILITY}}
- Do not add new dependencies

**Refactoring checklist — apply as many as are relevant:**
- [ ] Rename variables and functions to be more descriptive
- [ ] Extract repeated logic into reusable functions
- [ ] Reduce function length (aim for single responsibility)
- [ ] Remove dead code and unnecessary comments
- [ ] Simplify complex conditionals
- [ ] Replace magic numbers/strings with named constants
- [ ] Improve error handling
- [ ] Apply language idioms and best practices

**Output format:**
1. **Refactored code** — complete, runnable.
2. **Change log** — a bullet list of every change made and why.
3. **Behavior guarantee** — confirm that the public behavior is unchanged.
4. **Recommended next steps** — any further improvements that are out of scope for this refactor (e.g., adding tests, splitting into modules).
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{LANGUAGE}}` | Programming language | `Python`, `JavaScript` |
| `{{ORIGINAL_CODE}}` | The code to refactor | *(paste code here)* |
| `{{REFACTORING_GOALS}}` | Specific goals for this refactor | `Improve readability, reduce function complexity, add proper error handling` |
| `{{KEEP_API}}` | Public API that must not change | `yes — the process_order() function signature must stay the same`, `no` |
| `{{COMPATIBILITY}}` | Dependencies or environments to stay compatible with | `Python 3.8+`, `Node 16+` |

## Usage Notes

- Always specify what must NOT change — this prevents the model from breaking callers.
- If you have tests, run them after applying the refactoring to confirm behavior is preserved.
- For large files, refactor one class or module at a time.
