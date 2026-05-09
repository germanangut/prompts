---
title: "Research Summary"
description: "Summarize research on a topic into a structured briefing with sources"
category: analysis
type: prompt
tags: [research, summarization, literature-review, briefing]
agent_capabilities: [research, summarization, analysis]
use_when: "When you need a comprehensive summary of what is known about a topic"
version: "1.0"
---

# Research Summary

## Purpose

Use this prompt to get a structured research summary on any topic. Output includes key claims, evidence, conflicting views, knowledge gaps, and practical implications — all organized for fast decision-making.

## Prompt

```
You are a research analyst. Provide a structured research summary on the following topic.

**Topic:** {{TOPIC}}
**Purpose of the research:** {{PURPOSE}}
**Depth required:** {{DEPTH}}
**Key questions to answer:**
{{KEY_QUESTIONS}}

**Research Summary Structure:**

1. **Overview** (1 paragraph)
   - What is this topic and why does it matter?
   - Current state of knowledge in one paragraph.

2. **Key Claims and Findings**
   - Bullet list of the most important, well-supported findings
   - Each claim should note its strength: [Established] / [Emerging] / [Contested]

3. **Conflicting Views and Debates**
   - Where experts disagree
   - Main arguments on each side
   - Current consensus, if any

4. **Notable Evidence and Data**
   - Key statistics, studies, or cases that anchor the discussion
   - Flag any evidence that is outdated (> 5 years old for fast-moving fields)

5. **Knowledge Gaps**
   - What is not yet known
   - Where further research is needed

6. **Practical Implications**
   - What does this mean for {{PURPOSE}}?
   - Actionable recommendations based on current knowledge

7. **Suggested Sources**
   - List 5–10 types of sources to consult for deeper reading (journals, databases, key authors, etc.)
   - Note: Do not fabricate specific citations — suggest source types only unless you have high confidence in a specific reference.

**Caveats:**
- Clearly label any claims you are uncertain about.
- Note the knowledge cutoff date for any rapidly evolving topic.
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{TOPIC}}` | The research topic | `Retrieval-Augmented Generation (RAG) for enterprise AI` |
| `{{PURPOSE}}` | Why you need this research | `Deciding whether to adopt RAG for our internal knowledge base` |
| `{{DEPTH}}` | How deep to go | `Executive overview (2–3 pages)`, `Deep technical briefing` |
| `{{KEY_QUESTIONS}}` | Specific questions the summary must answer | `What are the main failure modes? What is the cost vs. benefit?` |

## Usage Notes

- Treat generated research summaries as a starting point — always verify key claims against primary sources.
- For fast-moving topics (AI, biotech, crypto), note that training data may be outdated.
- If you have source documents, paste them in and ask for a summary *of those documents* rather than general knowledge.
