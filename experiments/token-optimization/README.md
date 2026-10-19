# Token optimization experiments

Test potential optimizations such as:
- Smaller task-specific context instead of large repeated instructions.
- Targeted file search before opening whole files.
- Reusable repository guidance for stable conventions.
- Loading skills/knowledge only when relevant.
- Avoiding repeated summaries and redundant tool calls.
- Breaking large tasks into bounded steps with explicit handoff artifacts.

Record direct token metrics only when the agent exposes them. If not, record observable proxies and label them as proxies. Quality, tests, rework, and correctness must be measured alongside usage.
