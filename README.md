# AI-Driven Software Development

An evidence-based engineering case study for experienced developers who want to use AI coding agents effectively across the software development lifecycle—while controlling cost and preserving engineering quality.

## Demonstration application

**Task and Approval Management System**: a small, conventional application used to demonstrate requirements engineering, architecture, AI-assisted implementation, testing, context management, code search, reusable prompts, agent workflows, hooks, and optimization experiments.

The application is the test subject. The primary deliverable is a reproducible engineering methodology supported by code, prompts, measurements, and test evidence.

## Principles

- **Evidence before claims:** publish reproducible artifacts and real results, not invented metrics.
- **Human accountability:** AI-generated code, tests, and documents must be reviewed and verified.
- **Cost awareness:** use the existing AI environment and a documented low-cost subscription reference. Record actual plan limits and additional costs; do not imply the whole project is guaranteed to cost a fixed amount.
- **Build only what earns its complexity:** begin with ordinary repository search and clear instructions; introduce knowledge graphs, RAG, embeddings, or MCP only when an experiment justifies them.
- **Existing-codebase workflows matter:** cover feature development and bug fixing in unfamiliar, multi-module applications as well as new-app development.
- **Privacy and safety:** use synthetic data and public-safe examples. Never commit credentials, private agent configuration, employer code, or confidential data.
- **Deployment is optional:** a reproducible build, automated tests, E2E evidence, and documented release readiness can prove substantial lifecycle coverage without a public deployment.

## Repository map

- `specifications/` — problem statement, requirements, architecture, and API contracts.
- `ai-engineering/` — public-safe prompts, context guidance, skills, hooks, and workflow examples.
- `testing/` — test strategy, acceptance scenarios, and E2E workflows.
- `experiments/` — experiment plans and result templates for prompts, context, retrieval, and cost.
- `evidence/` — evidence index, measurement definitions, and reports.
- `articles/` — the article series in Markdown.

Folders are intentionally lightweight at the start. Add artifacts when they are useful; do not create empty infrastructure just to fill the tree.

## Start here

1. Read `ROADMAP.md`.
2. Review `specifications/problem-statement.md`.
3. Define the baseline in `experiments/BASELINE-EXPERIMENT.md` before optimizing anything.
4. Use `evidence/EVIDENCE-STANDARD.md` for every public claim.
5. Record decisions and measurements as work happens.
6. Publish articles only after their supporting evidence has been reviewed.

## Evidence labels

Use these labels consistently:

- **Measured:** directly captured using a documented method.
- **Verified:** independently reproduced or checked against a stated acceptance criterion.
- **Observed:** a qualitative observation from a documented run.
- **Estimated:** a calculation based on explicitly stated assumptions.
- **Planned:** not yet executed.
- **Not available:** the tool does not expose the measurement.

Do not describe a planned or estimated result as measured.

## Current status

This repository is a starter framework. No application implementation, test result, performance result, or cost result is claimed until it is actually produced and recorded.
