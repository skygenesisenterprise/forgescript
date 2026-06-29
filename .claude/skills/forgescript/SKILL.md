```markdown
# forgescript Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the `forgescript` TypeScript codebase. It covers file organization, import/export styles, commit message habits, and testing patterns. By following these guidelines, contributors can write consistent, maintainable code and collaborate effectively within the project.

## Coding Conventions

### File Naming
- All files use **kebab-case**.
  - Example: `my-module.ts`, `user-service.test.ts`

### Import Style
- Use **relative imports** for all modules.
  - Example:
    ```typescript
    import { myFunction } from './utils';
    ```

### Export Style
- Use **named exports** exclusively.
  - Example:
    ```typescript
    // In user-service.ts
    export function getUser() { ... }
    export const USER_ROLE = 'admin';
    ```

### Commit Messages
- Commit messages are **freeform** (no enforced prefix).
- Average message length: ~64 characters.
  - Example:  
    ```
    Fix bug in user authentication flow
    ```

## Workflows

### Adding a New Module
**Trigger:** When you need to create a new feature or utility.
**Command:** `/add-module`

1. Create a new `.ts` file using kebab-case (e.g., `feature-x.ts`).
2. Implement your logic using named exports.
3. Use relative imports to include dependencies.
4. Write a corresponding test file (see Testing Patterns).
5. Commit your changes with a clear, descriptive message.

### Refactoring Existing Code
**Trigger:** When improving or reorganizing existing code.
**Command:** `/refactor-code`

1. Identify the code to refactor.
2. Ensure file naming and imports follow conventions.
3. Update named exports as needed.
4. Adjust relative imports in dependent files.
5. Run tests to confirm nothing is broken.
6. Commit with a message describing the refactor.

### Writing Tests
**Trigger:** When adding or updating functionality.
**Command:** `/write-test`

1. Create a test file named `module-name.test.ts` alongside the module.
2. Use the project's preferred testing framework (unknown; check existing tests for style).
3. Write tests that cover all exported functions and constants.
4. Run the test suite to verify correctness.

## Testing Patterns

- Test files follow the pattern: `*.test.*` (e.g., `user-service.test.ts`).
- The testing framework is not explicitly defined; review existing tests to match style.
- Place test files near the modules they test.
- Cover all named exports with appropriate test cases.

  Example:
  ```typescript
  // user-service.test.ts
  import { getUser } from './user-service';

  describe('getUser', () => {
    it('returns the correct user', () => {
      // test logic here
    });
  });
  ```

## Commands
| Command         | Purpose                                    |
|-----------------|--------------------------------------------|
| /add-module     | Scaffold and implement a new module        |
| /refactor-code  | Refactor existing code to improve quality  |
| /write-test     | Add or update tests for a module           |
```
