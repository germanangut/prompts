---
title: "Agent Role Definition"
description: "Define an agent's role, goals, capabilities, and constraints for a multi-agent system"
category: agents
type: prompt
tags: [agent-config, role-definition, multi-agent, capability]
agent_capabilities: [agent-configuration, planning]
use_when: "When designing a new agent for a multi-agent system and you need to specify its role, boundaries, and interfaces"
version: "1.0"
---

# Agent Role Definition

## Purpose

Use this prompt to design a well-specified agent role within a larger system. The output is an agent specification document that defines what the agent does, what it needs, and how it integrates with other agents.

## Prompt

```
You are a systems architect specializing in multi-agent AI systems. Help me define the role of a new agent.

**System being built:** {{SYSTEM_DESCRIPTION}}
**Agent's intended function:** {{AGENT_FUNCTION}}
**Other agents in the system:** {{OTHER_AGENTS}}

**Generate a complete Agent Role Definition:**

---
## Agent Profile

**Agent Name:** [Name that reflects its function]
**Agent Type:** Specialist | Generalist | Orchestrator | Tool-executor | Evaluator
**Primary Goal:** One sentence stating the agent's main objective.
**Success Criteria:** How do we know this agent is doing its job well?

---
## Responsibilities

### Must Do (Core)
- [List 3–7 core responsibilities]

### Should Do (Extended)
- [List additional capabilities when capacity allows]

### Must NOT Do (Boundaries)
- [List explicit exclusions to prevent scope creep or safety issues]

---
## Inputs

| Input | Source | Format | Required? | Description |
|---|---|---|---|---|
| | | | | |

**Input validation rules:**
- [What makes an input valid vs. invalid?]
- [What happens with invalid inputs?]

---
## Outputs

| Output | Consumer | Format | Trigger | Description |
|---|---|---|---|---|
| | | | | |

---
## Tools and Capabilities

| Tool / Capability | Purpose | Access Level |
|---|---|---|
| | | Read / Write / Execute |

---
## Interaction Model

**Receives instructions from:** [human / orchestrator agent / event trigger]
**Reports results to:** [human / orchestrator / other agent]
**Can delegate to:** [list sub-agents or tools]
**Communication protocol:** [function call / message queue / REST / direct]

---
## Memory and State

**Needs persistent memory:** Yes / No
**State scope:** per-task | per-session | long-term
**What to remember:** [list key information to retain between calls]

---
## Error Handling

| Error Type | Detection | Response |
|---|---|---|
| Input invalid | | |
| Tool failure | | |
| Timeout | | |
| Ambiguous task | | |

---
## Evaluation Criteria

How to assess this agent's performance:
- [ ] Accuracy: [metric]
- [ ] Latency: [target]
- [ ] Reliability: [target uptime / success rate]
- [ ] Safety: [how to verify it stays in bounds]
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{SYSTEM_DESCRIPTION}}` | What the overall multi-agent system does | `An autonomous software development pipeline that takes requirements and delivers tested code` |
| `{{AGENT_FUNCTION}}` | What this specific agent should do | `Review code output from the coding agent and flag issues` |
| `{{OTHER_AGENTS}}` | Other agents in the system and their roles | `Planner agent (breaks tasks into subtasks), Coder agent (writes code), Tester agent (runs tests)` |

## Usage Notes

- Define one role per agent — resist the urge to create "do-everything" agents.
- The "Must NOT Do" section is as important as the "Must Do" — it prevents scope creep.
- Share this spec with the team and get alignment before building the agent.
