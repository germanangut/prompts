---
title: "Data Analysis"
description: "Analyze a dataset and surface key insights, trends, and anomalies"
category: analysis
type: prompt
tags: [data-analysis, insights, statistics, eda]
project_types: [data-science]
agent_capabilities: [analysis, data-analysis]
use_when: "When you have a dataset or data description and need to extract meaningful insights"
version: "1.0"
---

# Data Analysis

## Purpose

Use this prompt to perform exploratory data analysis (EDA) and extract actionable insights from a dataset. Works with raw data, summary statistics, or a description of a dataset.

## Prompt

```
You are a data analyst with expertise in statistics and data visualization. Analyze the following data.

**Dataset Description / Sample:**
{{DATASET}}

**Business Context:** {{BUSINESS_CONTEXT}}
**Analysis Goal:** {{ANALYSIS_GOAL}}

**Perform the following analysis:**

1. **Data Quality Assessment**
   - Missing values: which columns, what percentage, what to do about them
   - Outliers: identify and characterize
   - Data type issues or inconsistencies
   - Duplicate records

2. **Descriptive Statistics**
   - For numeric columns: mean, median, std dev, min, max, quartiles
   - For categorical columns: cardinality, top values and their frequencies
   - Distributions: note any skewness or bimodality

3. **Key Findings** (3–7 insights)
   - Each finding should be specific, quantified, and business-relevant
   - Format: **Finding:** [what] | **Evidence:** [numbers] | **Implication:** [so what]

4. **Correlations and Patterns**
   - Notable correlations between variables
   - Trends over time (if time-series data)
   - Segmentation patterns or clusters

5. **Anomalies and Risks**
   - Unexpected values or patterns
   - Data reliability concerns

6. **Recommended Visualizations**
   - List 3–5 charts that would best illustrate the key findings, with description of axes and what each reveals

7. **Next Steps**
   - Follow-on analyses recommended
   - Data collection gaps to address
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{DATASET}}` | The data to analyze — paste CSV sample, column descriptions, or summary stats | *(paste data or description here)* |
| `{{BUSINESS_CONTEXT}}` | Why this data exists and what business process it reflects | `Monthly sales transactions for an e-commerce store, 2022–2024` |
| `{{ANALYSIS_GOAL}}` | What decision or question this analysis should inform | `Understand why revenue dropped 20% in Q3 2024` |

## Usage Notes

- For large datasets, paste a representative 50–100 row sample plus the full column list with types.
- Including `{{BUSINESS_CONTEXT}}` is critical — it allows the model to prioritize findings that matter.
- If you have access to a Python/SQL environment, ask the model to generate analysis code instead.
