# prompts
Vibe coding courses
Below is the **complete 14-day interactive course structure** for validation. I designed it directly from your Advanced Master Prompt: local-first, advanced-user focused, dialogue-based, mentor-led, and optimized to produce a working **Agentic Job Hunter OS** in 14 days. 

# Advanced Vibe Coding: Build a Local-First Agentic Job Hunter OS

## Course Outcome

By the end of Day 14, the student should have a working local-first MVP that can:

Ingest resumes, ingest jobs, analyze fit, score opportunities, tailor resumes, generate outreach, prepare interview material, maintain semantic memory, orchestrate agents with LangGraph, automate workflows with n8n, run local models through Ollama, store structured and vector data, expose a React dashboard, and operate inside a Dockerized local environment.

The course is not a passive tutorial. Every day follows this loop:

**Explain → Ask → Build → Prompt → Validate → Debug → Improve → Reflect → Gate → Continue**

---

# System Architecture Being Built

## Core Stack

| Layer                  | Technology                                             |
| ---------------------- | ------------------------------------------------------ |
| Frontend               | React, Vite, TypeScript                                |
| Backend                | FastAPI, Python, Pydantic                              |
| Local AI               | Ollama                                                 |
| Agent Orchestration    | LangGraph                                              |
| Workflow Automation    | n8n                                                    |
| Structured DB          | PostgreSQL                                             |
| Vector DB              | Qdrant                                                 |
| Cache / Queue Optional | Redis                                                  |
| Infrastructure         | Docker Compose                                         |
| CI/CD                  | GitHub Actions                                         |
| Observability          | Logs, traces, evaluation reports, workflow audit trail |

---

# Target Agentic Job Hunter OS

## Main Capabilities

1. Resume ingestion
2. Job ingestion
3. Job/resume semantic matching
4. Fit scoring
5. ATS optimization
6. Resume tailoring
7. Cover letter generation
8. Recruiter outreach generation
9. Interview preparation
10. Job market intelligence
11. Semantic memory
12. Human approval workflow
13. Agent orchestration
14. n8n automation
15. AI evaluation harness
16. Local-first deployment
17. Portfolio-grade documentation

---

# Course Map at a Glance

| Day    | Theme                                  | Main Build Output                                   |
| ------ | -------------------------------------- | --------------------------------------------------- |
| Day 1  | Product, architecture, repo foundation | Architecture blueprint + monorepo scaffold          |
| Day 2  | Local AI foundation                    | Ollama + model strategy + local inference tests     |
| Day 3  | Backend foundation                     | FastAPI service + Pydantic schemas                  |
| Day 4  | Data foundation                        | PostgreSQL + Qdrant + resume/job schemas            |
| Day 5  | Resume ingestion                       | Resume parser + structured profile extraction       |
| Day 6  | Job ingestion                          | Job collector + normalized job model                |
| Day 7  | Semantic matching                      | Embeddings + Qdrant search + fit scoring v1         |
| Day 8  | Agent orchestration                    | LangGraph workflow for job analysis                 |
| Day 9  | Resume tailoring                       | Tailoring agent + human approval gate               |
| Day 10 | Outreach and interview prep            | Outreach agent + interview prep agent               |
| Day 11 | n8n automation                         | Automated job pipeline + notifications              |
| Day 12 | Frontend dashboard                     | React dashboard for jobs, scores, agents, approvals |
| Day 13 | Evaluation and observability           | Eval harness + logs + quality dashboard             |
| Day 14 | Hardening and portfolio delivery       | Dockerized MVP + demo script + roadmap              |

---

# Day 1 — Product Vision, Architecture, and Repo Foundation

## Learning Objective

Define the Job Hunter OS as a real software product, not a prompt experiment.

## Why It Matters

Agentic systems fail when builders start with prompts before defining boundaries, state, workflows, data ownership, approval points, and evaluation criteria.

## Architecture Context

Today establishes the whole system:

* What agents exist
* What workflows they control
* What humans must approve
* What data is stored
* What services own which responsibilities
* What “good output” means

## Mentor Dialogue

The course should ask:

* What is the primary user journey?
* Is the system optimizing for job volume, job quality, or strategic career fit?
* What should the AI be allowed to do automatically?
* What must always require human approval?
* What would make this system dangerous, annoying, or low-trust?
* What is the smallest useful MVP after 14 days?

## Hands-On Implementation

Create the monorepo:

```text
job-hunter-os/
  apps/
    web/
    api/
  services/
    agents/
    workflows/
    ingestion/
    evaluation/
  infra/
    docker/
  docs/
    architecture/
    prompts/
    evals/
```

Create initial docs:

```text
docs/architecture/system-context.md
docs/architecture/agent-map.md
docs/architecture/data-model.md
docs/architecture/human-approval-policy.md
```

## Suggested AI Prompt

```text
Act as a principal software architect. Help me define the MVP architecture for a local-first Agentic Job Hunter OS using React, FastAPI, Ollama, LangGraph, PostgreSQL, Qdrant, n8n, and Docker Compose.

Return:
1. Core user journeys
2. Agent responsibilities
3. Data entities
4. Human approval gates
5. Risks
6. MVP boundaries
7. What should not be automated yet
```

## Expected Output

By the end of Day 1, the learner has:

* A clear MVP scope
* A system context diagram
* A first agent taxonomy
* A repo scaffold
* A written approval policy
* A first version of the product backlog

## Validation Checklist

* Can you explain the system in 2 minutes?
* Can you identify the human approval points?
* Are the agents separated by responsibility?
* Is the MVP achievable in 14 days?
* Are data entities defined before code starts?
* Is the architecture local-first by default?

## Common Mistakes

* Starting with LangGraph too early
* Creating too many agents
* Treating agents as personalities instead of software components
* Skipping data modeling
* Letting the AI send outreach automatically
* Building the UI before defining workflows

## Readiness Gate

The learner can continue only if they can answer:

```text
What is the smallest version of this system that creates real job-search value without becoming unsafe or over-engineered?
```

---

# Day 2 — Local AI Foundation with Ollama

## Learning Objective

Install and validate the local AI layer.

## Why It Matters

The whole system depends on local-first inference. The learner must understand model tradeoffs, latency, quality, context limits, structured output behavior, and cost avoidance.

## Architecture Context

Ollama becomes the local model runtime used by:

* Resume extraction
* Job analysis
* Fit scoring explanations
* Resume tailoring
* Outreach generation
* Interview preparation

## Mentor Dialogue

Ask:

* Which tasks need reasoning models?
* Which tasks need fast lightweight models?
* Which tasks need embeddings?
* What happens if the local model hallucinates?
* How will we validate structured outputs?

## Hands-On Implementation

Install and test:

* Ollama
* At least one general reasoning model
* At least one coding-capable model
* One local embedding model if available

Create:

```text
services/agents/model_registry.py
services/agents/ollama_client.py
docs/architecture/model-strategy.md
```

## Model Strategy

Example model categories:

| Task                | Model Type                       |
| ------------------- | -------------------------------- |
| Resume parsing      | Reliable structured-output model |
| Job analysis        | Reasoning model                  |
| Fast classification | Smaller local model              |
| Embeddings          | Local embedding model            |
| Code generation     | Coding model                     |
| Draft generation    | Writing-capable model            |

## Suggested AI Prompt

```text
Act as a local AI systems architect. Help me design a model selection strategy for a local-first Job Hunter OS using Ollama.

For each capability, recommend:
1. Model category
2. Prompting strategy
3. Validation method
4. Failure mode
5. Fallback behavior
```

## Expected Output

* Ollama running locally
* Model registry created
* Test prompts executed
* Local model strengths and weaknesses documented
* First structured output experiment completed

## Validation Checklist

* Can the backend call Ollama?
* Can the model return JSON?
* Can invalid JSON be detected?
* Is there a fallback plan?
* Are model choices tied to tasks?

## Common Mistakes

* Assuming one model can do everything
* Ignoring latency
* Trusting JSON without validation
* Not logging prompts and outputs
* Using large models for simple classification

## Readiness Gate

The learner must demonstrate:

```text
A local model can receive a job description and return valid structured JSON with role title, seniority, required skills, preferred skills, and red flags.
```

---

# Day 3 — FastAPI Backend Foundation

## Learning Objective

Build the API foundation that all agents, workflows, and UI components will use.

## Why It Matters

Agent systems need stable service boundaries. The backend is the spine of the product.

## Architecture Context

FastAPI owns:

* API routes
* Data validation
* Calls to Ollama
* Calls to agents
* Persistence coordination
* Workflow triggers
* Approval state

## Mentor Dialogue

Ask:

* Which endpoints are user-facing?
* Which endpoints are internal workflow endpoints?
* What should be synchronous vs asynchronous?
* How should the system handle failed AI responses?
* What should be logged?

## Hands-On Implementation

Create FastAPI app:

```text
apps/api/
  main.py
  app/
    api/
    core/
    models/
    schemas/
    services/
    agents/
    db/
```

Create endpoints:

```text
GET /health
POST /resumes
POST /jobs
POST /analyze-fit
POST /agents/run
GET /jobs
GET /jobs/{id}
```

## Suggested AI Prompt

```text
Act as a senior FastAPI engineer. Generate a clean FastAPI project structure for a production-shaped MVP.

Requirements:
- Pydantic schemas
- health endpoint
- service layer
- error handling
- environment configuration
- placeholder routes for resumes, jobs, fit scoring, and agent execution

Do not over-engineer. Keep it MVP-ready but extensible.
```

## Expected Output

* Running FastAPI backend
* Clean project structure
* Pydantic request/response models
* Initial service layer
* Health check endpoint
* First local Ollama API call through backend

## Validation Checklist

* Does the API start reliably?
* Are schemas separate from business logic?
* Are errors structured?
* Are environment variables handled cleanly?
* Is the API ready for frontend integration?

## Common Mistakes

* Putting all logic in route handlers
* No schema validation
* No error model
* No service separation
* No environment config

## Readiness Gate

The learner can continue when:

```text
The API can accept a job description, call the local model, validate the response, and return structured analysis.
```

---

# Day 4 — Data Foundation: PostgreSQL and Qdrant

## Learning Objective

Design and implement the structured and semantic memory layers.

## Why It Matters

Agentic systems are only as useful as their memory model. PostgreSQL handles durable truth. Qdrant handles semantic retrieval.

## Architecture Context

PostgreSQL stores:

* Resumes
* Jobs
* Applications
* Fit scores
* Tailored outputs
* Approval status
* Agent runs
* Evaluation results

Qdrant stores:

* Resume chunks
* Job description chunks
* Skill embeddings
* Past outreach examples
* Interview prep context

## Mentor Dialogue

Ask:

* What belongs in relational storage?
* What belongs in vector storage?
* What should never be stored?
* How do we connect vector records to source-of-truth records?
* What is the difference between memory and truth?

## Hands-On Implementation

Create Docker services:

```yaml
postgres
qdrant
api
```

Create tables:

```text
resumes
resume_versions
jobs
job_sources
job_fit_scores
applications
agent_runs
approval_items
evaluation_results
```

Create Qdrant collections:

```text
resume_chunks
job_chunks
career_memory
outreach_examples
```

## Suggested AI Prompt

```text
Act as a data architect. Design a PostgreSQL and Qdrant schema for a local-first Job Hunter OS.

Separate:
1. Source-of-truth relational data
2. Semantic retrieval data
3. Audit and observability data
4. Human approval workflow data

Return table definitions, relationships, vector collection design, and risks.
```

## Expected Output

* PostgreSQL running locally
* Qdrant running locally
* Initial migrations or schema scripts
* DB connection from FastAPI
* Qdrant client connection from FastAPI

## Validation Checklist

* Are job and resume records durable?
* Can vector entries be traced back to original records?
* Is approval status represented?
* Is there an agent run audit trail?
* Can failed runs be inspected?

## Common Mistakes

* Storing everything as embeddings
* No relational source of truth
* No foreign-key relationship between vectors and records
* No audit trail
* No versioning of resume outputs

## Readiness Gate

Continue when:

```text
The system can store one resume, one job, create vector chunks for both, and retrieve related chunks through semantic search.
```

---

# Day 5 — Resume Ingestion and Profile Extraction

## Learning Objective

Build a resume ingestion pipeline that extracts structured candidate intelligence.

## Why It Matters

The resume becomes the foundation for fit scoring, tailoring, outreach, and interview prep.

## Architecture Context

Resume ingestion feeds:

* Candidate profile
* Skill graph
* Experience timeline
* Role alignment
* Semantic memory
* Resume tailoring agent

## Mentor Dialogue

Ask:

* What information should be extracted exactly?
* What should not be inferred?
* How do we detect unsupported claims?
* How do we preserve original resume truth?
* What makes resume parsing risky?

## Hands-On Implementation

Create pipeline:

```text
Upload resume
Extract raw text
Chunk resume
Generate embeddings
Extract structured candidate profile
Validate profile against schema
Store result
```

Create schema:

```text
CandidateProfile
Skill
Experience
Project
Education
Certification
Achievement
CareerTheme
```

## Suggested AI Prompt

```text
Act as a resume intelligence extraction engine.

Extract only what is supported by the resume text.

Return valid JSON matching this schema:
- candidate_summary
- skills
- roles
- years_of_experience
- industries
- achievements
- leadership_experience
- technologies
- certifications
- potential_target_roles
- extraction_confidence
- unsupported_inferences

Do not invent facts.
```

## Expected Output

* Resume ingestion endpoint
* Resume text extraction
* Structured profile JSON
* Pydantic validation
* Stored resume profile
* Embedded resume chunks

## Validation Checklist

* Does extraction avoid hallucinated facts?
* Are unsupported inferences flagged?
* Is the original resume preserved?
* Is the structured profile valid?
* Are chunks searchable in Qdrant?
* Is confidence captured?

## Common Mistakes

* Letting AI rewrite the resume too early
* Inferring skills not explicitly shown
* No confidence score
* No raw text preservation
* No validation against schema

## Readiness Gate

Continue when:

```text
The system can ingest a resume and produce a validated CandidateProfile without unsupported claims.
```

---

# Day 6 — Job Ingestion and Job Intelligence

## Learning Objective

Build a job ingestion pipeline that converts job posts into structured opportunity intelligence.

## Why It Matters

Job posts are messy. The system needs normalized data to score fit, detect red flags, and guide tailoring.

## Architecture Context

Job ingestion feeds:

* Fit scoring
* ATS matching
* Resume tailoring
* Outreach strategy
* Interview prep
* Market intelligence

## Mentor Dialogue

Ask:

* What makes a job worth pursuing?
* How should we distinguish required vs preferred skills?
* What red flags matter?
* What should the AI infer vs not infer?
* How should job quality be scored?

## Hands-On Implementation

Create job ingestion through:

* Manual paste
* URL placeholder
* CSV import placeholder

Create schema:

```text
JobPosting
Company
RoleRequirements
SkillRequirement
CompensationSignal
SenioritySignal
RedFlag
OpportunitySignal
```

## Suggested AI Prompt

```text
Act as a job intelligence analyst.

Analyze this job description and return valid JSON with:
- role_title
- company
- seniority_level
- required_skills
- preferred_skills
- responsibilities
- domain_signals
- leadership_signals
- compensation_signals
- remote_policy
- red_flags
- opportunity_quality_score
- extraction_confidence

Only infer when strongly supported.
```

## Expected Output

* Job ingestion endpoint
* Structured job profile
* Job embeddings
* Job quality score v1
* Red flag detection
* Stored job record

## Validation Checklist

* Are required and preferred skills separated?
* Are red flags justified?
* Is seniority classified correctly?
* Is confidence captured?
* Is the job searchable?
* Can the raw job post be retrieved?

## Common Mistakes

* Treating all skills equally
* Not identifying vague job posts
* Over-inferencing salary or remote policy
* No red-flag logic
* No source preservation

## Readiness Gate

Continue when:

```text
The system can ingest a job description and produce a validated structured JobPosting with red flags and required skills.
```

---

# Day 7 — Semantic Matching and Fit Scoring

## Learning Objective

Build the first real intelligence layer: resume-to-job matching.

## Why It Matters

This is where the system starts producing strategic value. But scoring must be explainable, not magical.

## Architecture Context

Fit scoring uses:

* Candidate profile
* Resume chunks
* Job profile
* Job chunks
* Skill overlap
* Semantic similarity
* Experience alignment
* Missing skills
* Strategic fit

## Mentor Dialogue

Ask:

* What does “fit” mean?
* Should fit be based on ATS match, career strategy, or likelihood of interview?
* How do we explain a score?
* What should lower the score?
* How do we avoid fake precision?

## Hands-On Implementation

Create scoring dimensions:

```text
skill_match_score
experience_match_score
seniority_match_score
domain_match_score
leadership_match_score
ats_keyword_score
strategic_fit_score
overall_fit_score
```

Create output:

```text
FitAnalysis
ScoreBreakdown
Strength
Gap
Recommendation
TailoringPriority
```

## Suggested AI Prompt

```text
Act as a career-fit scoring engine.

Compare the candidate profile and job profile.

Return valid JSON:
- overall_fit_score from 0 to 100
- score_breakdown
- top_strengths
- key_gaps
- ats_keywords_present
- ats_keywords_missing
- tailoring_recommendations
- apply_recommendation: strong_yes, yes, maybe, no
- explanation
- confidence

Do not exaggerate fit.
```

## Expected Output

* Fit scoring endpoint
* Fit score persisted
* Explainable score breakdown
* Semantic search used in scoring context
* Missing keyword analysis
* Apply/no-apply recommendation

## Validation Checklist

* Is the score explainable?
* Are gaps clearly identified?
* Are missing keywords real?
* Is the recommendation justified?
* Does the system avoid false confidence?
* Can two jobs be compared?

## Common Mistakes

* Producing one unexplained score
* Overweighting keyword overlap
* Ignoring seniority mismatch
* No strategic fit dimension
* Treating missing skills as automatic rejection

## Readiness Gate

Continue when:

```text
The system can compare one resume to three jobs and explain which job is the best target and why.
```

---

# Day 8 — LangGraph Agent Orchestration

## Learning Objective

Convert isolated AI calls into a controlled multi-step workflow.

## Why It Matters

Agentic systems require orchestration discipline. LangGraph gives structure, state, branching, retries, and human-in-the-loop gates.

## Architecture Context

Today introduces the first agent graph:

```text
Job Intake
→ Job Analysis
→ Resume Match
→ Fit Scoring
→ Recommendation
→ Human Review
→ Tailoring Queue
```

## Mentor Dialogue

Ask:

* What is the state object?
* Which steps are deterministic?
* Which steps need AI?
* Where can the workflow fail?
* Where should human approval happen?
* What should be retryable?

## Hands-On Implementation

Create:

```text
services/workflows/job_analysis_graph.py
services/workflows/state.py
services/agents/job_analyzer.py
services/agents/fit_scorer.py
services/agents/recommendation_agent.py
```

Define graph state:

```text
JobHunterState
resume_id
job_id
job_profile
candidate_profile
fit_analysis
approval_status
errors
trace_id
```

## Suggested AI Prompt

```text
Act as a LangGraph architect.

Design a graph workflow for job analysis using:
- job ingestion
- job structuring
- candidate matching
- fit scoring
- recommendation
- human approval gate

Return:
1. Nodes
2. Edges
3. State object
4. Failure handling
5. Retry strategy
6. Human-in-the-loop checkpoints
```

## Expected Output

* Working LangGraph workflow
* State object defined
* At least five workflow nodes
* Human approval placeholder
* Agent run logging
* Error handling

## Validation Checklist

* Is workflow state explicit?
* Are nodes single-purpose?
* Are failures captured?
* Can the graph be resumed?
* Is human approval modeled?
* Are agent runs logged?

## Common Mistakes

* Making one giant agent
* No graph state
* No retry logic
* No human checkpoints
* No traceability
* Agents calling agents without control

## Readiness Gate

Continue when:

```text
The learner can explain every node in the graph, what state it receives, what it returns, and what can fail.
```

---

# Day 9 — Resume Tailoring Agent with Human Approval

## Learning Objective

Build the resume tailoring capability safely and transparently.

## Why It Matters

Resume tailoring is high-value but risky. The system must improve relevance without inventing experience.

## Architecture Context

Tailoring uses:

* Candidate profile
* Original resume
* Job profile
* Fit analysis
* Missing ATS keywords
* Human approval workflow
* Versioned resume outputs

## Mentor Dialogue

Ask:

* What is ethical tailoring?
* What is exaggeration?
* What must never be changed?
* How should the system show edits?
* Should the system create a full resume or suggestions first?

## Hands-On Implementation

Create:

```text
TailoringRecommendation
ResumeEdit
ResumeVersion
ApprovalItem
```

Workflow:

```text
Fit analysis
→ Tailoring recommendations
→ Suggested resume edits
→ Human review
→ Approved tailored resume version
```

## Suggested AI Prompt

```text
Act as an ethical resume tailoring assistant.

Given:
1. Original resume text
2. Candidate profile
3. Job profile
4. Fit analysis

Suggest improvements that increase relevance without inventing experience.

Return valid JSON:
- summary_edits
- experience_bullet_edits
- keyword_alignment
- sections_to_reorder
- claims_that_must_not_be_added
- risk_notes
- approval_required_items
```

## Expected Output

* Tailoring agent
* Resume edit suggestions
* Human approval queue
* Versioned tailored resume
* Risk notes
* No fabricated claims

## Validation Checklist

* Are edits grounded in original resume?
* Are unsupported claims rejected?
* Are risky edits flagged?
* Is approval required?
* Is the original resume preserved?
* Is the tailored version versioned?

## Common Mistakes

* Fabricating achievements
* Adding skills not supported by experience
* Rewriting too aggressively
* No diff-style review
* No approval queue

## Readiness Gate

Continue when:

```text
The system can generate tailored resume suggestions and clearly separate safe edits from risky or unsupported edits.
```

---

# Day 10 — Outreach Agent and Interview Preparation Agent

## Learning Objective

Build two high-leverage agents: outreach generation and interview preparation.

## Why It Matters

The job hunter OS should support the full job pursuit cycle, not just scoring.

## Architecture Context

Outreach agent uses:

* Job profile
* Candidate profile
* Company context
* Fit strengths
* Human tone preference

Interview prep agent uses:

* Job responsibilities
* Candidate experience
* Gap analysis
* Likely questions
* STAR stories

## Mentor Dialogue

Ask:

* What makes recruiter outreach effective?
* What makes outreach sound fake?
* What tone should the candidate use?
* What interview questions are likely?
* How should gaps be prepared honestly?

## Hands-On Implementation

Create agents:

```text
recruiter_outreach_agent.py
interview_prep_agent.py
```

Create outputs:

```text
OutreachDraft
LinkedInMessage
EmailDraft
InterviewPrepPack
STARStory
QuestionBank
GapResponse
```

## Suggested Outreach Prompt

```text
Act as a recruiter outreach strategist.

Generate a concise outreach draft based on:
- candidate profile
- job profile
- fit strengths
- target tone: professional, warm, direct

Return:
- LinkedIn message under 700 characters
- email version
- subject line
- personalization notes
- risks or assumptions
```

## Suggested Interview Prompt

```text
Act as an interview preparation coach.

Create an interview prep pack for this role.

Return:
- likely interview themes
- technical questions
- behavioral questions
- STAR story suggestions
- gap-handling guidance
- company research questions
- questions to ask interviewer
```

## Expected Output

* Outreach generation endpoint
* Interview prep generation endpoint
* Human approval status for outreach
* Interview pack stored by job
* Reusable STAR story memory

## Validation Checklist

* Is outreach concise?
* Does it sound human?
* Is it grounded in real fit?
* Are interview answers honest?
* Are gaps addressed directly?
* Is outreach blocked from auto-send?

## Common Mistakes

* Generic outreach
* Overly long recruiter messages
* Fake enthusiasm
* No personalization
* Interview prep not tied to the actual job
* No approval workflow

## Readiness Gate

Continue when:

```text
The system can generate outreach and interview prep for one selected job, with all outbound content requiring approval.
```

---

# Day 11 — n8n Workflow Automation

## Learning Objective

Add automation without losing control.

## Why It Matters

n8n allows the system to automate job discovery, notifications, reminders, and workflow triggers while keeping the AI system modular.

## Architecture Context

n8n coordinates external or scheduled workflows:

```text
Daily job intake
→ API job ingestion
→ Fit scoring
→ Approval queue
→ Notification
```

## Mentor Dialogue

Ask:

* What should be automated?
* What should never be automated?
* What should happen daily?
* What requires human approval?
* How will automation failures be visible?

## Hands-On Implementation

Create n8n workflows:

1. Daily job ingestion placeholder
2. Manual trigger for job analysis
3. Notification when high-fit job appears
4. Approval reminder
5. Weekly job market summary

## Suggested AI Prompt

```text
Act as a workflow automation architect.

Design n8n workflows for a local-first Job Hunter OS.

Include:
- daily job ingestion
- high-fit job alert
- approval queue notification
- weekly market summary
- failure handling
- human approval checkpoints
```

## Expected Output

* n8n running in Docker Compose
* At least two working workflows
* n8n calling FastAPI
* FastAPI accepting workflow-triggered events
* Automation logs available

## Validation Checklist

* Does n8n call the API successfully?
* Are workflows idempotent?
* Are failures visible?
* Are human approvals preserved?
* Are high-fit alerts explainable?

## Common Mistakes

* Automating too much too early
* No retry logic
* No workflow naming convention
* No failure notifications
* Triggering duplicate jobs

## Readiness Gate

Continue when:

```text
A job can enter through an n8n workflow, be analyzed by the backend, and appear in the approval queue.
```

---

# Day 12 — React Dashboard

## Learning Objective

Build the user-facing control center for the Job Hunter OS.

## Why It Matters

Agentic systems need a good human control layer. The dashboard is where the user reviews, approves, rejects, and improves AI outputs.

## Architecture Context

The frontend exposes:

* Resume profile
* Job list
* Fit scores
* Job detail
* Tailoring recommendations
* Outreach drafts
* Interview prep packs
* Agent run logs
* Approval queue

## Mentor Dialogue

Ask:

* What does the user need to see first?
* What decisions must the interface support?
* What should be explainable?
* How do we prevent blind AI trust?
* Where should approval actions live?

## Hands-On Implementation

Create React app:

```text
apps/web/
  src/
    components/
    pages/
    api/
    types/
    hooks/
```

Build screens:

```text
Dashboard
Jobs
Job Detail
Resume Profile
Approval Queue
Agent Runs
Settings
```

## Suggested AI Prompt

```text
Act as a senior React + TypeScript engineer.

Design a clean dashboard for a local-first Agentic Job Hunter OS.

Screens:
- overview dashboard
- job list with fit scores
- job detail with score explanation
- approval queue
- resume tailoring review
- agent run logs

Use simple, maintainable components.
```

## Expected Output

* React app running
* API integration
* Job list visible
* Fit score detail visible
* Approval queue visible
* Agent run logs visible

## Validation Checklist

* Can the user understand why a job scored high?
* Can the user approve or reject AI outputs?
* Are risky outputs visible?
* Is the UI simple?
* Is API typing clean?
* Does the frontend avoid hiding agent uncertainty?

## Common Mistakes

* UI that only shows final outputs
* No explainability
* No approval action
* No loading/error states
* No TypeScript types aligned with backend schemas

## Readiness Gate

Continue when:

```text
The dashboard lets the user review a job, understand the fit score, inspect AI outputs, and approve or reject generated content.
```

---

# Day 13 — Evaluation, Observability, and Reliability

## Learning Objective

Add the quality system needed to trust agent outputs.

## Why It Matters

Without evaluation and observability, the system is just a demo. Production-shaped AI requires logs, metrics, traces, test cases, and regression checks.

## Architecture Context

Evaluation covers:

* Resume extraction quality
* Job extraction quality
* Fit scoring consistency
* Tailoring safety
* Outreach quality
* Interview prep usefulness
* JSON validity
* Hallucination risk

Observability covers:

* Agent run logs
* Prompt versions
* Model used
* Inputs/outputs
* Latency
* Error rates
* Human approval decisions

## Mentor Dialogue

Ask:

* How do we know the AI output is good?
* What should be tested automatically?
* What requires human judgment?
* What metrics matter?
* How do we catch regressions?

## Hands-On Implementation

Create evaluation framework:

```text
services/evaluation/
  test_cases/
  evaluators/
  reports/
```

Create eval dimensions:

```text
json_validity
schema_compliance
grounding_score
hallucination_risk
usefulness_score
tone_quality
tailoring_safety
fit_score_reasonableness
```

## Suggested AI Prompt

```text
Act as an AI evaluation engineer.

Design an evaluation harness for a local-first Job Hunter OS.

Evaluate:
- resume extraction
- job extraction
- fit scoring
- resume tailoring
- outreach drafts
- interview prep

Include:
- automated checks
- human review checks
- regression test cases
- scoring rubric
- reporting format
```

## Expected Output

* Eval test cases
* Eval runner
* Eval report format
* Agent run logging
* Prompt versioning convention
* Basic observability dashboard or logs screen

## Validation Checklist

* Are prompts versioned?
* Are model outputs logged?
* Can bad JSON be detected?
* Can hallucination risk be flagged?
* Can old and new outputs be compared?
* Are human approvals used as feedback?

## Common Mistakes

* No evals
* Only testing happy paths
* No prompt version tracking
* No model metadata
* No human feedback loop
* No regression dataset

## Readiness Gate

Continue when:

```text
The learner can run an evaluation suite and identify at least three output quality problems before production use.
```

---

# Day 14 — Hardening, Demo, Portfolio, and Roadmap

## Learning Objective

Package the MVP into a portfolio-grade local-first agentic system.

## Why It Matters

The goal is not only to build the app but to demonstrate advanced engineering judgment.

## Architecture Context

Today consolidates:

* Docker Compose
* README
* Architecture docs
* Demo data
* Demo script
* Known limitations
* Security notes
* Roadmap
* Portfolio narrative

## Mentor Dialogue

Ask:

* What is working?
* What is fragile?
* What is intentionally out of scope?
* What would be needed for production?
* What would impress a technical reviewer?
* What would worry a technical reviewer?

## Hands-On Implementation

Finalize:

```text
docker-compose.yml
README.md
docs/architecture/final-architecture.md
docs/demo/demo-script.md
docs/security/local-first-risk-review.md
docs/roadmap/v1-v2-roadmap.md
```

Create final demo flow:

```text
1. Upload resume
2. Ingest job
3. Analyze job
4. Score fit
5. Review recommendation
6. Generate tailoring suggestions
7. Approve edits
8. Generate outreach
9. Generate interview prep
10. View agent logs
11. Run evaluation report
```

## Suggested AI Prompt

```text
Act as a staff engineer reviewing my Agentic Job Hunter OS MVP.

Evaluate:
- architecture quality
- agent boundaries
- local-first design
- data model
- human approval workflow
- evaluation system
- security risks
- portfolio readiness
- what to improve next

Be direct and practical.
```

## Expected Output

* Working Dockerized MVP
* Final architecture document
* Demo script
* Portfolio README
* Known limitations
* V1/V2 roadmap
* Evaluation report
* Final readiness review

## Validation Checklist

* Can the full system run locally?
* Can a reviewer understand the architecture?
* Are limitations honest?
* Are risks documented?
* Are agent workflows visible?
* Is the MVP demoable in under 10 minutes?
* Is the project portfolio-grade?

## Common Mistakes

* No documentation
* Demo depends on hidden manual steps
* No known limitations
* No security review
* No eval report
* No clear next roadmap

## Final Readiness Gate

The student completes the course when they can answer:

```text
What makes this system an engineered agentic product rather than a collection of prompts?
```

---

# Cross-Course Agent Taxonomy

The system should include these agents.

| Agent                     | Responsibility             | Automation Level             |
| ------------------------- | -------------------------- | ---------------------------- |
| Resume Intelligence Agent | Parse and structure resume | Assisted                     |
| Job Intelligence Agent    | Parse job descriptions     | Assisted                     |
| Fit Scoring Agent         | Compare resume and job     | Assisted                     |
| ATS Optimization Agent    | Identify missing keywords  | Assisted                     |
| Resume Tailoring Agent    | Suggest resume edits       | Human approval required      |
| Outreach Agent            | Draft recruiter messages   | Human approval required      |
| Interview Prep Agent      | Generate prep material     | Assisted                     |
| Market Intelligence Agent | Summarize trends           | Assisted                     |
| Evaluation Agent          | Review AI output quality   | Assisted                     |
| Orchestrator              | Route workflow state       | Controlled through LangGraph |

Important principle: these are **software responsibilities**, not “characters.”

---

# Human Approval Policy

## Always Requires Human Approval

* Resume edits
* Cover letters
* Recruiter outreach
* LinkedIn messages
* Applications
* Claims added to resume
* Anything sent externally

## Can Be Automated Locally

* Job parsing
* Resume parsing
* Fit scoring
* Semantic search
* Draft generation
* Interview prep generation
* Evaluation checks
* Internal notifications

## Should Not Be Automated in MVP

* Applying to jobs automatically
* Sending recruiter messages automatically
* Modifying LinkedIn profile automatically
* Claiming skills not supported by resume
* Creating fake achievements
* Scraping sites in violation of terms

---

# Core Prompt Library

## 1. Architecture Prompt

```text
Act as a principal AI systems architect.

Review this feature for a local-first Agentic Job Hunter OS.

Evaluate:
1. Service boundary
2. Data ownership
3. Agent responsibility
4. Human approval needs
5. Security risks
6. Evaluation requirements
7. MVP implementation path
```

## 2. Code Generation Prompt

```text
Act as a senior software engineer.

Generate implementation code for this component.

Constraints:
- Keep responsibilities separated
- Use typed schemas
- Include error handling
- Avoid hidden global state
- Make code testable
- Explain tradeoffs
- Do not over-engineer
```

## 3. Debugging Prompt

```text
Act as a debugging partner.

Given this error, help me:
1. Identify the likely root cause
2. Explain why it happened
3. Suggest a minimal fix
4. Suggest a durable fix
5. Add a regression test or validation step
```

## 4. Validation Prompt

```text
Act as a strict reviewer.

Validate this AI output against:
1. Schema correctness
2. Grounding in source text
3. Hallucination risk
4. Missing fields
5. Unsupported claims
6. Production readiness

Return pass/fail and corrections.
```

## 5. Refactoring Prompt

```text
Act as a staff engineer.

Review this code for:
1. Responsibility separation
2. Maintainability
3. Testability
4. Error handling
5. Naming
6. Extensibility
7. Over-engineering

Suggest a practical refactor.
```

---

# Evaluation Framework

## Evaluation Dimensions

| Dimension          | What It Checks                            |
| ------------------ | ----------------------------------------- |
| Schema validity    | Does output match Pydantic model?         |
| Grounding          | Is output supported by source text?       |
| Hallucination risk | Did the model invent facts?               |
| Usefulness         | Is the output actionable?                 |
| Safety             | Does output require approval?             |
| Tone               | Is outreach human and professional?       |
| Fit logic          | Is score explainable?                     |
| Repeatability      | Does similar input produce stable output? |
| Traceability       | Can we see model, prompt, input, output?  |

## Minimum Eval Test Cases

1. Strong-fit job
2. Weak-fit job
3. Overqualified job
4. Underqualified job
5. Vague job description
6. Job with red flags
7. Resume with unclear skills
8. Resume with leadership-heavy profile
9. Job requiring unsupported skill
10. Outreach generation test
11. Resume tailoring safety test
12. Interview prep usefulness test

---

# Daily Time Estimate

For an advanced learner:

| Day Type                    | Estimated Hours |
| --------------------------- | --------------: |
| Architecture and setup days |       3–4 hours |
| Backend/data/AI build days  |       4–6 hours |
| Orchestration days          |       5–6 hours |
| Frontend day                |       4–6 hours |
| Evaluation/hardening days   |       5–7 hours |

Total expected effort:

**60–75 focused hours over 14 days**

Minimum viable aggressive path:

**45–55 hours**

Comfortable implementation path:

**75–90 hours**

---

# My Validation Take

The topic coverage is strong and coherent. The course has the right progression:

1. **Architecture before agents**
2. **Local AI before workflows**
3. **Data model before intelligence**
4. **Intelligence before orchestration**
5. **Human approval before automation**
6. **UI after backend workflows**
7. **Evaluation before final demo**

The only topic I would consider adding explicitly is:

## Optional Day 0 — Environment Readiness

Before Day 1, add a short setup checkpoint:

* Python version
* Node version
* Docker Desktop
* GitHub repo
* Ollama installed
* VSCode extensions
* PowerShell/terminal sanity check
* Local disk requirements
* GPU/CPU expectations

This avoids wasting Day 1 on machine setup.

My recommendation: keep the **14 days as the build course**, but add **Day 0 as a prerequisite setup checklist**.
