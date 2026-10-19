# Hooks and automation

Add public-safe examples only after confirming the chosen agent supports the specific hook lifecycle and configuration.

Possible checks:
- Formatting and linting.
- Targeted unit tests.
- Secret scanning.
- Diff-size or protected-file checks.
- Required human approval before high-impact actions.

For each hook, document trigger, command, expected behavior, failure handling, permissions, and a reproducible test. Never claim a hook ran unless logs or another artifact prove it.
