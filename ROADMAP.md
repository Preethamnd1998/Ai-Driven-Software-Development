# Roadmap — AI-Driven Software Development

The series documents one end-to-end experiment, not 24 unrelated opinion pieces. Each article should link to its source artifacts, commits, and evidence.

## Part I — Establish the evidence

1. **AI-Driven Software Development: A Practical Engineering Experiment** — scope, constraints, baseline, evidence rules.
2. **From Idea to Requirements with AI** — problem statement, MRD/BRD where useful, stories, acceptance criteria, traceability.
3. **From Requirements to Architecture and Implementation Plans** — system design, API contracts, data model, task decomposition.

## Part II — Build an application with AI

4. **Building a New Application with a Constrained AI Budget** — incremental implementation, actual usage and developer effort.
5. **Prompt Engineering for Software Development** — comparable prompt variants and objective evaluation.
6. **AI Coding Agents: Planning, Execution and Human Approval** — bounded tasks, review gates, tool permissions.
7. **Context Engineering for Large Codebases** — repository instructions, architecture notes, task-specific context.
8. **Token Optimization Without Sacrificing Quality** — redundant reads, prompt size, retries, tool calls, quality checks.
9. **Hooks, Skills, Commands and Reusable Workflows** — automate repeatable checks where supported; measure impact.

## Part III — Test and improve quality

10. **AI-Assisted Unit, Integration and API Testing** — test generation and defect-detection evidence.
11. **End-to-End Testing with AI** — create, submit, approve/reject, verify status.
12. **AI-Assisted Debugging, Code Review and Regression Prevention** — reproduce, diagnose, fix, retest.
13. **Measuring AI Engineering Quality** — correctness, rework, elapsed time, developer effort, cost, limitations.

## Part IV — Work effectively in existing applications

14. **Using AI to Understand an Existing Codebase** — repository map, entry points, dependencies.
15. **Efficient File Search and Context Retrieval** — targeted search versus broad exploration.
16. **Building a Knowledge Graph for Codebase Understanding** — entities, relationships, query tasks, baseline comparison.
17. **RAG and Embeddings for Engineering Knowledge** — retrieval relevance, grounding, latency, indexing and maintenance costs.
18. **MCP and Tool Integration for Coding Agents** — narrow permissions, useful actions, security and auditability.
19. **Safely Adding Features to an Existing Application** — impact analysis through regression verification.
20. **AI-Assisted Bug Fixes Across Multiple Modules** — trace dependencies, bound changes, validate fixes.

## Part V — Reusable engineering practices

21. **Combining Context, Knowledge Graphs, RAG, MCP and Agent Workflows** — compare when each is justified; do not over-engineer.
22. **Reusable AI Engineering Playbooks** — prompts, checklists, workflows, evaluation criteria.
23. **From Development to Release Readiness** — builds, CI, dependencies, security checks, versioning. Deployment is optional.
24. **Final Results: What AI Actually Improved** — evidence, costs, failures, trade-offs, limitations and reusable conclusions.

## Per-article publication gate

Before publication, confirm:
- The claim is supported by a source artifact or measured result.
- The relevant prompt/configuration and test/evaluation steps are included where safe.
- Baseline and comparison methods are described for comparative claims.
- Limits, failures, and confounding factors are stated.
- No secrets, real patient data, private employer code, or unsupported compliance claims are present.
- The article clearly distinguishes measured, verified, observed, estimated, planned, and unavailable information.
