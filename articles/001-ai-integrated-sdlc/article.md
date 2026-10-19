# AI-Driven Software Development: A Practical Engineering Experiment

> **Draft — pending peer review.** This article is unpublished and has no publication date. It describes a plan, method, and verified results from an exploratory pilot experiment (Pilot 001).

## The engineering question

Experienced developers are being told that AI coding agents change how software gets built. Fewer people publish reproducible evidence about *where* they help across the whole lifecycle, what they cost, and where they fail.

This series asks one question: **how can an experienced developer use AI coding agents effectively across the software development lifecycle while controlling cost and preserving engineering quality?**

## Context and constraints

The series is one end-to-end experiment, not a collection of unrelated opinions. The roadmap ([`ROADMAP.md`](../../ROADMAP.md)) outlines 24 planned articles in five parts: establishing evidence, building an application with AI, testing and quality, working in existing codebases, and reusable practices.

The test subject is a deliberately conventional **Task and Approval Management System** ([problem statement](../../specifications/problem-statement.md)). The application is not the point; the methodology and its evidence are.

Constraints:
- **Cost awareness.** The work uses an existing AI environment and a documented low-cost subscription reference. Actual plan limits and any extra costs will be recorded; no fixed total cost is promised.
- **Privacy.** Synthetic data and public-safe examples only. No credentials, private agent configuration, employer code or confidential data.
- **Deployment is optional.** A reproducible build, automated tests and documented release readiness can show lifecycle coverage without a public deployment.
- **No premature complexity.** Start with ordinary repository search and clear instructions. Knowledge graphs, RAG, embeddings or MCP are introduced only when an experiment justifies them.

## Method

### Evidence rules
Every public claim follows the [Evidence Standard](../../evidence/EVIDENCE-STANDARD.md): state the claim, link its source, explain how it was collected, record environment and assumptions, disclose failures, and separate measurements from estimates. Six labels are used consistently: *Measured, Verified, Observed, Estimated, Planned, Not available*.

### Baseline first
Nothing is optimized before a baseline exists. The [baseline experiment](../../experiments/BASELINE-EXPERIMENT.md) implements one small vertical slice and records, among other things, commit SHA, agent and plan, context supplied, developer active versus elapsed time, available usage metrics (or `Not available`), tests run, defects and rework. Later experiments change one major variable at a time and compare like with like.

Experiment plans exist for [prompt evaluation](../../experiments/prompt-evaluation/README.md), [context retrieval](../../experiments/context-retrieval/README.md) and [token optimization](../../experiments/token-optimization/README.md). Measurements will be recorded in the [measurement log](../../evidence/MEASUREMENT-LOG.csv) and reported with the [experiment report template](../../experiments/EXPERIMENT-REPORT-TEMPLATE.md). The [test strategy](../../testing/TEST-STRATEGY.md) defines how quality is checked.

### Human accountability
AI-generated code, tests and documents are reviewed and verified by a person. Test coverage is not treated as proof of correctness.

## Evidence and results

### Pilot 001 — Two-Arm Implementation Study

**Status: Verified.** AI SDLC Pilot 001 executed a controlled comparison of two AI-integrated workflows on a frozen Mini Approval API specification (3 REST endpoints, 15 JUnit acceptance criteria, 3 process-level criteria, 18 total).

**Arm A (Direct Claude Code):** Human developer used Claude Code CLI directly (Claude Sonnet 5.5). Completed implementation in **68 minutes active effort** with zero defects and 18/18 acceptance criteria passed (15/15 JUnit + 3 process-level).

**Arm B (Enterprise AI Platform):** Human developer used Enterprise AI Platform v4.13.0 `/dev` workflow (Claude Opus 5.5, lazy-loaded standards, MCP allowlist, approval gate). Completed implementation in **75 minutes active effort** with zero defects and 18/18 acceptance criteria passed (15/15 JUnit + 3 process-level).

**Timing difference:** Arm B took 7 minutes longer (10.3% overhead). Both arms discovered zero critical/high defects during defect-discovery session. Both passed identical frozen test suite (15/15 tests). No rework required in either arm.

**Confounders:** Model difference (Sonnet 5.5 vs. Opus 5.5), learning effect (Arm A ran first), single run per arm, small feature scope. Cannot isolate workflow overhead from model capability differences with this design.

**Detailed evidence:** See [Pilot 001 Final Audit Report](../../experiments/pilot-001/ARM-A-B-AUDIT-REPORT-FINAL.md) for independently verified test results, measurement logs, and comprehensive confounder analysis. Frozen artifacts (protocol, specification, acceptance suite) remain unchanged.

## Failures and limitations

- A single developer, one demonstration application and a single run per workflow will not generalize to every team or codebase.
- Tool behaviour, plan limits and models change; every result is tied to a date and configuration (Pilot 001: 2026-10-20, macOS 27.0.0, Java 21.0.12, Maven 3.9.9).
- Some tools do not expose usage data (Pilot 001: prompt/turn counts, MCP access logs). Those gaps will be labelled *Not available*, not filled with estimates presented as measurements.
- Model capability differences (Claude Sonnet 5.5 vs. Opus 5.5) and learning effect (Arm A ran first) are documented but cannot be isolated in this two-arm design.
- The timing difference (10.3% overhead in Arm B) aligns with workflow procedural overhead (approval gate, standards review) but cannot be conclusively attributed to platform architecture alone.

## Reusable takeaways

1. **Define the question and evidence rules before running experiments.** Pilot 001 froze specification (SPEC.md), protocol (PROTOCOL.md), and acceptance suite (AcceptanceSuiteTest.java) at commit [`73d3fb9`](https://github.com/Preethamnd1998/Ai-Driven-Software-Development/commit/73d3fb9) before either implementation began, preventing measurement backfill. Pre-registration of all acceptance criteria (AC-01–AC-18) ensured neither arm could weaken requirements after seeing results.

2. **Establish a baseline before optimizing.** Arm A (Direct Claude Code) served as the baseline with no platform-specific features; Arm B (Enterprise AI Platform) varied one major workflow dimension (approval gates, lazy-loaded standards, MCP allowlist) for direct comparison. Both arms used identical feature specifications and environment (Java 21.0.12, Maven 3.9.9, Spring Boot 3.3.0, macOS 27.0.0) to isolate workflow variables.

3. **Change one variable at a time and keep raw evidence.** Pilot 001 isolated workflow changes (CLI vs. platform `/dev`) while controlling for frozen feature scope, test suite, and environment. Contemporaneous time-logs (time-log.csv), defect-logs (defect-log.csv), and acceptance results (acceptance-results.csv) in commits [`aa4bd62`](https://github.com/Preethamnd1998/Ai-Driven-Software-Development/commit/aa4bd62) and [`6711736`](https://github.com/Preethamnd1998/Ai-Driven-Software-Development/commit/6711736) provide reproducible audit trail with no backfill patterns.

4. **Label what is measured, verified, observed, estimated, planned or unavailable.** Pilot 001 evidence labeled: timing and test results marked *Verified* (independently re-executed); model versions marked *Observed* (recorded in contemporaneous logs); prompt counts and MCP access logs marked *Not available* (gaps disclosed in "Failures and limitations"). See [`PEER-REVIEW-REPORT.md`](../../experiments/pilot-001/PEER-REVIEW-REPORT.md) §2 for detailed evidence categorization.

5. **Publish failures and limits alongside successes.** Pilot 001 reports zero defects in both arms and identical test pass rates (18/18 criteria, 15/15 JUnit); also discloses single-run sample, model capability differences (Sonnet 5.5 vs. Opus 5.5), sequential execution learning effect, small feature scope (75 min), and inability to isolate workflow cost from model capability. See [`ARM-A-B-AUDIT-REPORT-FINAL.md`](../../experiments/pilot-001/ARM-A-B-AUDIT-REPORT-FINAL.md) §7 for complete confounder analysis.

## Artifacts

See [`references.md`](references.md) for linked repository artifacts.

### Pilot 001 Evidence Archive

- **Frozen scaffold commit:** [`73d3fb9`](https://github.com/Preethamnd1998/Ai-Driven-Software-Development/commit/73d3fb9) — Protocol, specification, acceptance suite, and experiment structure frozen before either implementation began (2026-10-20)
- **Arm A implementation:** [`aa4bd62`](https://github.com/Preethamnd1998/Ai-Driven-Software-Development/commit/aa4bd62) — Direct Claude Code workflow: Mini Approval API implementation, measurement logs, acceptance results, and AC-18 status correction (68 active minutes)
- **Arm B implementation:** [`6711736`](https://github.com/Preethamnd1998/Ai-Driven-Software-Development/commit/6711736) — Enterprise AI Platform `/dev` workflow: identical Mini Approval API implementation, platform plan, measurement logs, and acceptance results (75 active minutes)

Each commit includes the frozen acceptance suite run results, contemporaneous time-logs (time-log.csv, defect-log.csv, acceptance-results.csv), and supporting evidence. See [`ARM-A-B-AUDIT-REPORT-FINAL.md`](../../experiments/pilot-001/ARM-A-B-AUDIT-REPORT-FINAL.md) and [`PEER-REVIEW-REPORT.md`](../../experiments/pilot-001/PEER-REVIEW-REPORT.md) for independent verification and detailed analysis.
