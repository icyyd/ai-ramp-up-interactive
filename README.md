# The AI Ramp-Up: Interactive Edition

> **Disclaimer:** This project is for educational purposes only. It was built to serve a specific personal learning need and is shared as-is, with no guarantee of accuracy, completeness, or fitness for any other purpose.

A self-contained, chapter-by-chapter learning program taking you from AI fundamentals to forward-deployed practice and AI platform leadership. It is aligned with what Cloud Engineering, AI Engineering, Data Engineering, AI Platform Engineering, Applied AI, and AI Product Management postings actually ask for — including forward-deployed and Senior Manager/Director tracks — covering the full platform stack: models, prompting and context engineering, the modern data stack (Snowflake, Databricks, dbt), the streaming and lakehouse backbone (Kafka, S3, Hive, Iceberg, Spark SQL, Trino/Presto), operational databases and search (Postgres, Aurora MySQL, Cassandra, DynamoDB, Elasticsearch), RAG and agents (MCP, LangGraph), evals, runtime and orchestration (Docker, Kubernetes, Nomad, Airflow), cloud AI platforms (Bedrock, Vertex AI, Azure AI Foundry), FinOps, and AI security and governance.

**Live site:** [icyyd.github.io/ai-ramp-up-interactive](https://icyyd.github.io/ai-ramp-up-interactive/)

## Contents

### AI Ramp-Up curriculum

Thirteen chapters, roughly 230 to 280 hours total. Each chapter includes:

- A one-line rationale and tech chips showing what stack it covers
- Learning objectives
- Curated free-first resources with links (paid options clearly marked)
- Industry certifications relevant to that layer of the stack, with typical exam costs and a linked prep path (free wherever one exists) so exam preparation is part of the program itself
- A hands-on field exercise, several of which double as portfolio artifacts
- A self-check quiz with instant feedback

### Connected Interview Lab

The Interview Lab is a separate, connected module for senior cloud security and platform leadership interviews. It includes:

- A live cheatsheet built for glancing at mid-call: opening and closing lines, defensible numbers, a question router mapping likely questions to the answer and its proof, the five-stage technical flow, a do-not-say list, and questions to ask the interviewer
- A **Live mode** toggle that collapses the study material down to only the at-a-glance sections, and remembers the setting
- A job-description alignment map connecting experience to role requirements
- Cloud security evidence covering identity, application security, Kubernetes runtime protection, vulnerability remediation, and audit readiness
- Concise elevator, security-depth, leadership, and technical talk tracks
- A five-stage security-data architecture answer: collect, normalize, add context, prioritize, and deliver
- Cloud security governance and AI-agent guardrails
- Eight expandable STAR cases with credibility checks and proof points to prepare
- A time-boxed study plan with 15 primary-source learning links
- A quick-reference acronym glossary and independently saved rehearsal checklist

## Running it

The project is a static site with two HTML entry points, no build step, and no dependencies beyond Google Fonts.

- Open `index.html` directly in a browser and use the connected-module link to open `interview-lab.html`, or
- Serve it: `python3 -m http.server` then visit `http://localhost:8000`, or
- Host it on GitHub Pages: Settings → Pages → deploy from the main branch root.

## Progress persistence

Progress (resource checkmarks, quiz answers, chapter completion) saves automatically through a small storage adapter:

- Inside a claude.ai artifact, it uses the artifact storage API
- Self-hosted or opened locally, it falls back to `localStorage`
- If neither exists, progress lasts for the session only

The main curriculum is keyed as `airampup:v2`; the Interview Lab uses `airampup:interview-lab:v1`. Clearing site data resets saved progress.

## Structure

- `index.html` contains the main experience and the `CHAPTERS` curriculum array. Each chapter object defines its id, number, title, tag, time estimate, tech chips, objectives, resources, project, and quiz.
- `interview-lab.html` contains the standalone interview-preparation module and links back to the main curriculum.

Chapter `id` values key saved progress, so keep them stable when editing the curriculum. The chapter dial and navigation adapt automatically when the `CHAPTERS` array changes.
