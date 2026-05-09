---
title: "Pipeline Architecture"
description: "Design a data or integration pipeline architecture"
category: automation
type: prompt
tags: [pipeline, data-engineering, etl, integration, architecture]
project_types: [data-science, automation, devops]
agent_capabilities: [automation, planning, architecture]
use_when: "When you need to design a new data pipeline, ETL process, or integration pipeline"
version: "1.0"
---

# Pipeline Architecture

## Purpose

Use this prompt to design a complete data or integration pipeline. Output includes component design, data flow, technology selection, scalability considerations, and an implementation roadmap.

## Prompt

```
You are a data engineering architect. Design a pipeline for the following requirement.

**Pipeline Goal:** {{PIPELINE_GOAL}}
**Data Sources:** {{DATA_SOURCES}}
**Data Volume:** {{DATA_VOLUME}}
**Latency Requirement:** {{LATENCY}}
**Destination / Sink:** {{DESTINATION}}
**Available Infrastructure:** {{INFRASTRUCTURE}}
**Constraints:** {{CONSTRAINTS}}

**Design the pipeline with these components:**

1. **Pipeline Overview**
   - Type: Batch | Streaming | Micro-batch | Lambda (batch + streaming)
   - Recommended architecture pattern and rationale

2. **Data Flow Diagram (text form)**
   Source → [Ingestion] → [Processing] → [Storage] → [Serving]
   Show each component and the data that flows between them.

3. **Component Design**
   For each component:
   - Name and responsibility
   - Recommended technology and why
   - Input format / schema
   - Output format / schema
   - Throughput and scalability characteristics

4. **Ingestion Layer**
   - How data is pulled or pushed from sources
   - Change detection / CDC strategy (if applicable)
   - Schema evolution handling

5. **Processing / Transformation Layer**
   - Transformation logic
   - Data quality checks and validation rules
   - Error handling: quarantine, dead-letter, retry

6. **Storage Layer**
   - Raw zone (landing)
   - Processed / curated zone
   - Serving layer (if different)
   - Partitioning and indexing strategy

7. **Orchestration**
   - How pipeline runs are scheduled and monitored
   - Dependency management between jobs
   - Recommended orchestrator (Airflow, Prefect, etc.)

8. **Observability**
   - Metrics to track (latency, throughput, error rate, data freshness)
   - Alerting thresholds
   - Data lineage tracking

9. **Technology Stack Recommendation**
   - Full stack with justification
   - Alternatives considered and why rejected

10. **Implementation Roadmap**
    - Phase 1: MVP (what to build first)
    - Phase 2: Scale and reliability
    - Phase 3: Optimization and advanced features
```

## Variables

| Variable | Description | Example |
|---|---|---|
| `{{PIPELINE_GOAL}}` | What the pipeline should achieve | `Ingest clickstream events, enrich with user data, and serve real-time dashboards` |
| `{{DATA_SOURCES}}` | Source systems and their formats | `Kafka topic (JSON events), PostgreSQL users table, S3 product catalog (Parquet)` |
| `{{DATA_VOLUME}}` | Data size and throughput | `5M events/day, 500 events/sec peak, 2TB/month` |
| `{{LATENCY}}` | Acceptable delay from source to destination | `< 5 seconds end-to-end` (streaming) or `daily batch by 6am` |
| `{{DESTINATION}}` | Where processed data should go | `ClickHouse for analytics, Redis for real-time APIs` |
| `{{INFRASTRUCTURE}}` | What's already available | `AWS (EKS, S3, RDS), Kafka cluster, existing Airflow` |
| `{{CONSTRAINTS}}` | Budget, team, or technical constraints | `< $10k/month, team of 2 data engineers, must use AWS` |

## Usage Notes

- Start with the latency requirement — it drives the entire architecture (batch vs. streaming).
- Over-engineer observability from day one — it's far harder to add later.
- Validate the schema and data quality assumptions before committing to the architecture.
