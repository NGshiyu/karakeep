```markdown
# karakeep Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns, coding conventions, and workflows used in the `karakeep` TypeScript codebase. You'll learn how to contribute new backend features, update API routers, write and organize tests, and manage CI workflows in a consistent, maintainable way.

## Coding Conventions

- **Language:** TypeScript
- **Framework:** None detected
- **File Naming:** Use `camelCase` for file names.
  - Example: `subscriptionRouter.ts`, `userCommands.ts`
- **Import Style:** Use relative imports.
  - Example:
    ```typescript
    import { getUser } from './userUtils';
    ```
- **Export Style:** Use named exports.
  - Example:
    ```typescript
    export function createSubscription() { ... }
    ```
- **Commit Messages:** Follow [Conventional Commits](https://www.conventionalcommits.org/) with prefixes like `feat`, `fix`, `docs`, `chore`, `ci`.
  - Example: `feat: add subscription cancellation endpoint`

## Workflows

### Feature Development: API Router and Tests
**Trigger:** When you want to add or fix a backend API feature, especially related to subscriptions or admin commands.  
**Command:** `/new-api-feature`

1. **Edit or create a router file** in `packages/trpc/routers/*.ts` to implement or update API logic.
   - Example:
     ```typescript
     // packages/trpc/routers/subscriptionRouter.ts
     export const subscriptionRouter = ...
     ```
2. **Edit or create a corresponding test file** in `packages/trpc/routers/*.test.ts`.
   - Example:
     ```typescript
     // packages/trpc/routers/subscriptionRouter.test.ts
     import { subscriptionRouter } from './subscriptionRouter';
     test('should cancel subscription', () => { ... });
     ```
3. **Optionally, update related CLI command files** in `apps/cli/src/commands/*.ts` if your feature affects CLI behavior.
   - Example:
     ```typescript
     // apps/cli/src/commands/cancelSubscription.ts
     export function cancelSubscriptionCommand() { ... }
     ```

### CI Workflow Update
**Trigger:** When you want to change how CI runs, such as enabling/disabling tests or updating build logic.  
**Command:** `/update-ci`

1. **Edit the CI workflow file** at `.github/workflows/ci.yml` to change CI behavior.
   - Example:
     ```yaml
     # .github/workflows/ci.yml
     jobs:
       test:
         runs-on: ubuntu-latest
         steps:
           - uses: actions/checkout@v3
           - run: pnpm install
           - run: pnpm test
     ```
2. **Optionally, update package or lock files** (`pnpm-lock.yaml`, `pnpm-workspace.yaml`) if dependencies or test coverage change.

## Testing Patterns

- **Test Files:** Place test files alongside routers, using the pattern `*.test.ts`.
  - Example: `packages/trpc/routers/subscriptionRouter.test.ts`
- **Testing Framework:** Not explicitly detected; use standard TypeScript test conventions.
- **Test Example:**
  ```typescript
  import { myApiRouter } from './myApiRouter';

  test('returns expected data', () => {
    const result = myApiRouter.someMethod();
    expect(result).toBe('expected');
  });
  ```

## Commands

| Command          | Purpose                                                         |
|------------------|-----------------------------------------------------------------|
| /new-api-feature | Start a new API feature or update an existing router and tests. |
| /update-ci       | Update CI workflow or related dependency files.                 |
```
