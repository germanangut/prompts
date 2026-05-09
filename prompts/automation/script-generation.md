---
title: "Script Generation"
description: "Generate a script to automate a repetitive or complex task"
category: automation
type: prompt
tags: [script, automation, bash, python, cli]
project_types: [automation, devops]
agent_capabilities: [code-generation, automation]
use_when: "When you need a script to automate a specific task — file processing, API calls, data transformation, system administration"
version: "1.0"
---

# Script Generation

## Purpose

Use this prompt to generate a complete, production-quality automation script. Works for shell scripts, Python scripts, JavaScript/Node.js scripts, and more.

## Prompt

```
You are an expert in scripting and automation. Generate a {{LANGUAGE}} script that automates the following task.

**Task:** {{TASK_DESCRIPTION}}
**Input:** {{INPUT_DESCRIPTION}}
**Output:** {{OUTPUT_DESCRIPTION}}
**Environment:** {{ENVIRONMENT}}
**Error handling requirements:** {{ERROR_REQUIREMENTS}}

**Script requirements:**
- Language: {{LANGUAGE}}
- Must handle: {{EDGE_CASES}}
- Must NOT do: {{EXCLUSIONS}}
- Performance requirement: {{PERFORMANCE}}

**Generate:**

1. **The complete script** with:
   - Shebang line and file header comment explaining purpose, usage, and author placeholder
   - Argument parsing / configuration section (use argparse for Python, getopts for bash, etc.)
   - Main logic with clear function decomposition
   - Comprehensive error handling: check exit codes, validate inputs, handle missing files/APIs
   - Logging: INFO for normal operation, ERROR for failures (to stderr or log file)
   - Idempotency: the script should be safe to run multiple times
   - Dry-run mode: a `--dry-run` flag that shows what would happen without doing it

2. **Usage examples:**
   \`\`\`bash
   # Example 1: basic usage
   # Example 2: with options
   # Example 3: dry run
   \`\`\`

3. **Dependencies:** List any libraries or tools to install before running.

4. **Testing instructions:** How to verify the script works correctly.

5. **Caveats and known limitations.**
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{LANGUAGE}}` | Scripting language | `Python 3`, `Bash`, `Node.js` |
| `{{TASK_DESCRIPTION}}` | What the script should do | `Read all CSV files in a directory, filter rows where status == "active", and output a merged CSV` |
| `{{INPUT_DESCRIPTION}}` | Input format and source | `Directory of CSV files, each with columns: id, name, status, created_at` |
| `{{OUTPUT_DESCRIPTION}}` | Expected output | `A single merged.csv file with only active rows, sorted by created_at` |
| `{{ENVIRONMENT}}` | Where the script runs | `Ubuntu 22.04, Python 3.11, cron job` |
| `{{ERROR_REQUIREMENTS}}` | How errors should be handled | `Log errors and continue; send Slack alert if > 10 rows fail` |
| `{{EDGE_CASES}}` | Edge cases to handle | `Empty files, malformed CSV rows, missing columns, duplicate IDs` |
| `{{EXCLUSIONS}}` | Things the script must NOT do | `Do not modify original files; do not delete anything` |
| `{{PERFORMANCE}}` | Performance requirements | `Must process 1M rows in < 60 seconds` |

## Usage Notes

- Always include `--dry-run` when your script makes writes, deletes, or API calls.
- Test on a small sample before running on production data.
- Add the script to version control with a meaningful commit message describing what it automates.
