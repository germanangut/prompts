# 🧠 Prompts — Master Library

A structured, agent-readable library of prompts organized by **type**, **domain**, and **project category**. Designed to be used both by humans and by autonomous agents that need to discover, select, and apply the right prompt for any task or automation.

---

## 📚 What's in This Library

| Section | Description |
|---|---|
| [`prompts/`](./prompts/) | Reusable prompts organized by category (coding, writing, analysis, automation, agents, general) |
| [`projects/`](./projects/) | Project-scoped prompt sets for specific domains (web dev, data science, DevOps, etc.) |
| [`agents/`](./agents/) | Agent definitions and system-prompt templates for autonomous agents |
| [`index.json`](./index.json) | Machine-readable catalog — the entry point for autonomous agents |
| [`STRUCTURE.md`](./STRUCTURE.md) | Full annotated map of the library |

---

## 🗂️ Prompt Categories

### [`prompts/coding/`](./prompts/coding/)
Prompts for software engineering tasks: code generation, review, debugging, refactoring, testing.

### [`prompts/writing/`](./prompts/writing/)
Prompts for content creation: blog posts, technical documentation, READMEs, reports.

### [`prompts/analysis/`](./prompts/analysis/)
Prompts for data analysis, research, summarization, and critical thinking.

### [`prompts/automation/`](./prompts/automation/)
Prompts for designing and building workflow automations, scripts, and pipelines.

### [`prompts/agents/`](./prompts/agents/)
System prompts and meta-prompts for configuring AI agents and multi-agent systems.

### [`prompts/general/`](./prompts/general/)
General-purpose prompts that apply across multiple domains.

---

## 🏗️ Project Categories

| Folder | Use case |
|---|---|
| [`projects/web-development/`](./projects/web-development/) | Frontend, backend, full-stack web projects |
| [`projects/data-science/`](./projects/data-science/) | EDA, ML pipelines, notebooks, dashboards |
| [`projects/automation/`](./projects/automation/) | RPA, scripts, workflow bots |
| [`projects/content-creation/`](./projects/content-creation/) | Blogs, social media, newsletters |
| [`projects/mobile-app/`](./projects/mobile-app/) | iOS, Android, cross-platform apps |
| [`projects/devops/`](./projects/devops/) | CI/CD, infrastructure, cloud deployments |

---

## 🤖 For Autonomous Agents

If you are an autonomous agent reading this library:

1. **Start with [`index.json`](./index.json)** — it contains a structured catalog of every prompt, its category, tags, and file path.
2. Use the `type` field to filter by prompt category.
3. Use the `project_type` field to find prompts scoped to a specific project domain.
4. Use the `agent_capabilities` array to find prompts suited to your capabilities.
5. Each prompt file includes a YAML front-matter block with metadata (title, description, tags, use_when).

### Example agent workflow
```
1. Read index.json
2. Filter entries where type == "coding" AND tags include "refactoring"
3. Load the referenced prompt file
4. Inject context and execute
```

---

## ✍️ Contributing

See [`CONTRIBUTING.md`](./CONTRIBUTING.md) for guidelines on adding new prompts, naming conventions, and metadata requirements.

---

## 📐 Conventions

- Every prompt file is a **Markdown file** with YAML front-matter metadata.
- Every directory has a **`README.md`** describing its contents.
- Prompt filenames use **kebab-case**.
- The `index.json` is updated whenever a prompt is added or modified.
