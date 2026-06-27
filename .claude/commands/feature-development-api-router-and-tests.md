---
name: feature-development-api-router-and-tests
description: Workflow command scaffold for feature-development-api-router-and-tests in karakeep.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-development-api-router-and-tests

Use this workflow when working on **feature-development-api-router-and-tests** in `karakeep`.

## Goal

Implements or updates a backend feature by modifying a TRPC router, updating or adding corresponding tests, and sometimes touching related command or admin files.

## Common Files

- `packages/trpc/routers/*.ts`
- `packages/trpc/routers/*.test.ts`
- `apps/cli/src/commands/*.ts`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit or create a file in packages/trpc/routers/*.ts to implement or update API logic.
- Edit or create a corresponding test file in packages/trpc/routers/*.test.ts.
- Optionally, update related files such as apps/cli/src/commands/*.ts for CLI commands.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.