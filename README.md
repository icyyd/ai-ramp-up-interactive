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

The Interview Lab is a separate, connected module for a senior cloud and AI security leadership interview. It is structured as questions with the answer underneath, built from the STAR work examples and VP framework source document.

- **Target-organization values** — each mapped to where it naturally lands in an answer rather than recited
- **36 questions in eight groups** — opening and fit, identity and privileged access, AI and agents, secure delivery, compliance assurance, incident response, program and strategy, and a credibility self-check. Each opens to a result-first line plus the track that matches the room.
- **Four work examples and an incident-response lifecycle** — consolidated JIT privileged access, the production Cloud Engineering Agent, shift-left delivery, and agentic SOC 2 continuous control assurance, each with hiring-manager and developer talk tracks, technical depth on request, and clearly labeled résumé-verified figures, calibrated estimates, or proposed targets
- **Claim boundaries** — aligned to the August 19, 2026 Platform Engineering résumé plus direct clarification: the Tricentis remit consistently combined Cloud Platform Security and governance, Cloud Platform/Infrastructure Engineering, and DevOps; SecOps was the analyst partner; and the Cloud Engineering Agent progressed from pilot to production use for performance and security RCA
- **VP cloud and AI security program** — Govern, Enable, Control, Observe, Prove; five AI autonomy tiers from open experimentation to privileged action; eight non-negotiable agent guardrails; the operating model; executive metrics; and a 30/90/6-month/12-month roadmap
- A **Call index** pinned in the sidebar, a **Live mode** toggle that collapses answers and hides instructional prose, and an acronym glossary
- Reference frameworks: NIST CSF 2.0, SP 800-61r3, AI RMF and GenAI Profile, Fed SR 26-2, NY DFS, CSA CCM and AICM, OWASP Agentic Top 10, MITRE ATLAS, CISA, and AICPA TSC

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

The main curriculum is keyed as `airampup:v2`; the Interview Lab stores only its Live mode setting, under `airampup:interview-lab:mode:v1`. Clearing site data resets saved progress.

## Structure

- `index.html` contains the main experience and the `CHAPTERS` curriculum array. Each chapter object defines its id, number, title, tag, time estimate, tech chips, objectives, resources, project, and quiz.
- `interview-lab.html` contains the standalone interview-preparation module, structured as a question-and-answer reference over four STAR work examples and a VP program framework, and links back to the main curriculum.

Chapter `id` values key saved progress, so keep them stable when editing the curriculum. The chapter dial and navigation adapt automatically when the `CHAPTERS` array changes.
