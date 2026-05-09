---
title: "Write Tests"
description: "Generate comprehensive test cases for a function, class, or module"
category: coding
type: prompt
tags: [testing, unit-tests, tdd, quality]
agent_capabilities: [code-generation, testing]
use_when: "When you need to write unit, integration, or end-to-end tests for existing or new code"
version: "1.0"
---

# Write Tests

## Purpose

Use this prompt to generate a comprehensive test suite for a given piece of code. The model will identify edge cases, error conditions, and happy paths, then produce tests in the appropriate testing framework.

## Prompt

```
You are a software engineer who writes thorough, high-quality tests. Generate tests for the following {{LANGUAGE}} code.

**Code to test:**
\`\`\`{{LANGUAGE}}
{{CODE}}
\`\`\`

**Testing framework:** {{TEST_FRAMEWORK}}
**Test type:** {{TEST_TYPE}}
**Coverage goal:** {{COVERAGE_GOAL}}

**Generate tests that cover:**
1. **Happy path** — all inputs are valid and the function behaves as expected.
2. **Edge cases** — boundary values, empty inputs, zero, null/None, very large inputs.
3. **Error cases** — invalid inputs, missing required fields, type mismatches.
4. **Side effects** — ensure mocks/stubs are used for external dependencies (DB, APIs, file system).
5. **Concurrency** (if applicable) — race conditions or thread safety issues.

**Output format:**
1. Complete test file ready to run with {{TEST_FRAMEWORK}}.
2. A brief comment above each test explaining what it verifies.
3. A coverage summary table listing: scenario, test name, expected result.
4. Any additional tests you recommend adding that are out of scope for now.

**Constraints:**
- Do not test implementation details — only public behavior.
- Mocks should be clearly labeled.
- Each test should have a single, clear assertion focus.
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{LANGUAGE}}` | Programming language | `Python`, `TypeScript`, `Java` |
| `{{CODE}}` | The code to write tests for | *(paste function/class here)* |
| `{{TEST_FRAMEWORK}}` | Testing framework to use | `pytest`, `Jest`, `JUnit 5`, `Go testing` |
| `{{TEST_TYPE}}` | Type of tests to write | `unit`, `integration`, `end-to-end` |
| `{{COVERAGE_GOAL}}` | Target coverage | `100% branch coverage`, `cover all public methods` |

## Usage Notes

- For integration tests, describe the external dependencies so the model knows what to mock.
- If you have existing tests, include them so the model avoids duplicating coverage.
- Run the generated tests immediately after — some may need minor tweaks for your environment.
