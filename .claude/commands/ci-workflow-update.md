---
name: ci-workflow-update
description: Workflow command scaffold for ci-workflow-update in karakeep.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /ci-workflow-update

Use this workflow when working on **ci-workflow-update** in `karakeep`.

## Goal

Updates the continuous integration workflow, often to enable/disable tests or adjust build steps.

## Common Files

- `.github/workflows/ci.yml`
- `pnpm-lock.yaml`
- `pnpm-workspace.yaml`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit .github/workflows/ci.yml to change CI behavior.
- Optionally, update related package or lock files if dependencies or test coverage change.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.