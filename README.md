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

The Interview Lab is a separate, connected module for senior cloud security and platform leadership interviews. It is built around two things: anticipating the question, and having a work sample ready to prove the answer.

- A **question bank** of 42 likely questions in six groups — opening and positioning, platform and architecture, security and scenarios, AI and agentic, leadership, and curveballs. Each row is *if they ask → lead with → go to*, where "go to" names the work sample or deep answer that proves it.
- **Eight STAR work samples**, each with situation, task, action, result, lesson, and the proof points to have ready
- A compact open-and-close card: the twenty-second opening, defensible numbers, a do-not-say list, questions to ask the interviewer, and a closing line
- A **Call index** pinned in the sidebar linking straight to each question group, so navigation stays fast under pressure
- A **Live mode** toggle that hides instructional prose, collapses long-form answers to scannable titles, and remembers the setting
- Deep answers behind the hints: the five-stage security-data architecture answer, a cloud security program model of five planes (identity, delivery, runtime, data, assurance) each with an explicit "what AI changes" column, and talk tracks covering developer AI freedom versus control, securing an agentic system, reviewing AI-generated code, and agent accountability
- Forward-looking proposals, clearly labelled as proposals rather than past work: a tiered AI autonomy model, the paved road that implements it, and the architecture mapped to AWS services
- A quick-reference acronym glossary and JD lens

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
- `interview-lab.html` contains the standalone interview-preparation module, built around a question bank and a STAR work-sample library, and links back to the main curriculum.

Chapter `id` values key saved progress, so keep them stable when editing the curriculum. The chapter dial and navigation adapt automatically when the `CHAPTERS` array changes.
