---
title: "Blog Post Writer"
description: "Write a complete, engaging blog post on any topic"
category: writing
type: prompt
tags: [blog, content, writing, seo]
project_types: [content-creation]
agent_capabilities: [writing, content-generation]
use_when: "When you need to produce a full blog post from a topic or outline"
version: "1.0"
---

# Blog Post Writer

## Purpose

Use this prompt to generate a complete, well-structured, and engaging blog post. The output is publication-ready with a compelling introduction, organized body sections, and a strong conclusion.

## Prompt

```
You are an expert content writer and editor. Write a complete blog post based on the following brief.

**Topic:** {{TOPIC}}
**Target Audience:** {{AUDIENCE}}
**Tone:** {{TONE}}
**Desired Word Count:** {{WORD_COUNT}}
**Target Keywords (for SEO):** {{KEYWORDS}}
**Goal of the Post:** {{GOAL}}

**Structure:**
1. **Headline** — Write 3 headline options (one question-based, one number-based, one statement-based) and recommend the best.
2. **Introduction** (150–200 words) — Hook the reader, establish the problem or opportunity, preview what the post covers.
3. **Body** — Divide into {{SECTION_COUNT}} logical sections. Each section should have:
   - A clear subheading (H2 or H3)
   - 2–4 paragraphs of substantive content
   - A key takeaway or actionable tip
4. **Conclusion** (100–150 words) — Summarize key points, provide a call to action.
5. **Meta Description** — 150–160 characters for SEO.

**Style guidelines:**
- Use active voice.
- Keep sentences concise (avg < 20 words).
- Use examples, analogies, or data to support claims.
- Avoid jargon unless writing for a technical audience.
- Include {{KEYWORDS}} naturally — do not keyword-stuff.
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{TOPIC}}` | The main subject of the post | `How to use AI agents to automate repetitive tasks` |
| `{{AUDIENCE}}` | Who will read this | `Software developers with intermediate Python skills` |
| `{{TONE}}` | Writing tone | `Conversational and informative`, `Authoritative and technical` |
| `{{WORD_COUNT}}` | Approximate word count | `1200`, `2000` |
| `{{KEYWORDS}}` | SEO target keywords | `AI automation, Python agents, workflow automation` |
| `{{GOAL}}` | What the post should achieve | `Educate readers and drive sign-ups for our tool` |
| `{{SECTION_COUNT}}` | Number of body sections | `4`, `6` |

## Usage Notes

- The more specific the topic and audience, the better the output.
- Review the three headline options and pick the one that fits your brand voice.
- Always fact-check any statistics or claims generated before publishing.
