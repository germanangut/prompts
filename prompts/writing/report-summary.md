---
title: "Report and Summary Writer"
description: "Summarize research, data, or documents into a clear, structured report"
category: writing
type: prompt
tags: [report, summary, writing, analysis]
agent_capabilities: [writing, summarization, analysis]
use_when: "When you need to distill a large body of information into a concise, structured report"
version: "1.0"
---

# Report and Summary Writer

## Purpose

Use this prompt to convert raw information (research findings, data, meeting notes, documents) into a clear, structured report with an executive summary, key findings, and recommendations.

## Prompt

```
You are a professional report writer. Create a structured report based on the following information.

**Report Title:** {{REPORT_TITLE}}
**Report Type:** {{REPORT_TYPE}}
**Audience:** {{AUDIENCE}}
**Source Material:**
{{SOURCE_MATERIAL}}

**Report structure:**

1. **Executive Summary** (150–200 words)
   - Purpose of the report
   - Key findings (3–5 bullet points)
   - Primary recommendation

2. **Background / Context** (optional)
   - Why this report was commissioned
   - Scope and limitations

3. **Key Findings**
   - Organize findings by theme or priority
   - Use subheadings for each major finding
   - Support each finding with data or evidence from the source material
   - Highlight any surprising or counterintuitive results

4. **Analysis**
   - What the findings mean
   - Trends, patterns, or risks identified
   - Comparison to benchmarks or previous periods (if applicable)

5. **Recommendations**
   - Numbered list of actionable recommendations
   - For each: what to do, why, and by when

6. **Next Steps**
   - Immediate actions (within 30 days)
   - Medium-term actions (30–90 days)
   - Owner suggestions for each action

**Style:**
- Use plain language — avoid jargon.
- Lead with conclusions, not process.
- Quantify findings wherever possible.
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{REPORT_TITLE}}` | Title of the report | `Q3 2024 Marketing Performance Report` |
| `{{REPORT_TYPE}}` | Type of report | `Performance report`, `Research summary`, `Incident post-mortem`, `Market analysis` |
| `{{AUDIENCE}}` | Who will read this | `Executive leadership`, `Engineering team`, `Board of directors` |
| `{{SOURCE_MATERIAL}}` | Raw content to summarize | *(paste notes, data, research findings, meeting transcript, etc.)* |

## Usage Notes

- The richer the source material, the more actionable the report output will be.
- For data-heavy reports, include the raw data or summary statistics in `{{SOURCE_MATERIAL}}`.
- Always have a domain expert validate the recommendations before presenting to stakeholders.
