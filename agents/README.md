# Agents

Complete agent definitions, system prompts, and configuration templates for autonomous AI agents.

## Agent Types

| Directory | Agent Type | Best for |
|---|---|---|
| [`research/`](./research/) | Research Agent | Searching, summarizing, fact-checking |
| [`coding/`](./coding/) | Coding Agent | Code generation, review, debugging, testing |
| [`planning/`](./planning/) | Planning Agent | Task decomposition, project planning, prioritization |
| [`orchestrator/`](./orchestrator/) | Orchestrator Agent | Coordinating multiple specialist agents |

## How to Use Agent Definitions

Each agent file contains:
1. **Front-matter metadata** — for catalog and discovery via `index.json`
2. **System Prompt** — the complete prompt to use when configuring the agent
3. **Agent Configuration Notes** — recommended temperature, max tokens, tools
4. **Deployment Example** — code snippet showing how to instantiate the agent

## Building a Multi-Agent System

A typical multi-agent system uses:

```
OrchestratorAgent
├── ResearchAgent      ← handles information gathering
├── CodingAgent        ← handles code tasks
└── PlanningAgent      ← handles planning and prioritization
```

1. Start with the [`orchestrator-agent.md`](./orchestrator/orchestrator-agent.md) system prompt.
2. Populate the `{{AGENT_TEAM}}` variable with your specialist agent descriptions.
3. Each specialist uses its own system prompt from this directory.
4. Wire them together using your agent framework of choice (LangGraph, CrewAI, AutoGen, custom).

## Adding New Agent Types

Follow the format in [`system-prompt-template.md`](../prompts/agents/system-prompt-template.md) and use [`agent-role-definition.md`](../prompts/agents/agent-role-definition.md) to design the role before writing the system prompt.
