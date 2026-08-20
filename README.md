# The AI Ramp-Up: Interactive Edition

> **Disclaimer:** This project is for educational purposes only. It was built to serve a specific personal learning need and is shared as-is, with no guarantee of accuracy, completeness, or fitness for any other purpose.

A self-contained, chapter-by-chapter learning program taking you from AI fundamentals to forward-deployed practice and AI platform leadership. It is aligned with what Cloud Engineering, AI Engineering, Data Engineering, AI Platform Engineering, Applied AI, and AI Product Management postings actually ask for — including forward-deployed and Senior Manager/Director tracks — covering the full platform stack: models, prompting and context engineering, the modern data stack (Snowflake, Databricks, dbt), the streaming and lakehouse backbone (Kafka, S3, Hive, Iceberg, Spark SQL, Trino/Presto), operational databases and search (Postgres, Aurora MySQL, Cassandra, DynamoDB, Elasticsearch), RAG and agents (MCP, LangGraph), evals, runtime and orchestration (Docker, Kubernetes, Nomad, Airflow), cloud AI platforms (Bedrock, Vertex AI, Azure AI Foundry), FinOps, and AI security and governance.

## Contents

Thirteen chapters, roughly 230 to 280 hours total. Each chapter includes:

- A one-line rationale and tech chips showing what stack it covers
- Learning objectives
- Curated free-first resources with links (paid options clearly marked)
- Industry certifications relevant to that layer of the stack, with typical exam costs and a linked prep path (free wherever one exists) so exam preparation is part of the program itself
- A hands-on field exercise, several of which double as portfolio artifacts
- A self-check quiz with instant feedback

The connected Interview Lab is a separate module with a JD-aligned architecture cheatsheet, cloud security and governance evidence, AI guardrails, concise talk tracks, an eight-case STAR bank, a time-boxed study plan with primary-source links, a quick-reference acronym glossary, and an independent rehearsal checklist for senior cloud security and platform leadership interviews.

## Running it

It is a single HTML file with no build step and no dependencies beyond Google Fonts.

- Open `index.html` directly in a browser and use the connected-module link to open `interview-lab.html`, or
- Serve it: `python3 -m http.server` then visit `http://localhost:8000`, or
- Host it on GitHub Pages: Settings → Pages → deploy from the main branch root.

## Progress persistence

Progress (resource checkmarks, quiz answers, chapter completion) saves automatically through a small storage adapter:

- Inside a claude.ai artifact, it uses the artifact storage API
- Self-hosted or opened locally, it falls back to `localStorage`
- If neither exists, progress lasts for the session only

Progress is keyed as `airampup:v2`. Clearing site data resets it.

## Structure

All content lives in the `CHAPTERS` array at the top of the script block in `index.html`. Each chapter is one object: id, number, title, tag, time estimate, tech chips, objectives, resources, project, and quiz. To add or edit a chapter, edit that array; numbering on the dial and navigation adapts automatically. Chapter `id` values key saved progress, so keep them stable across edits.

The Interview Lab is intentionally separate in `interview-lab.html`. It links back to the main ramp-up and stores its rehearsal checklist under its own `airampup:interview-lab:v1` key.
