---
name: minimal-fix
description: Fix a reported bug or narrowly scoped problem using the smallest reasonable code change. Use when the user wants a surgical fix without unrelated refactoring or architecture changes.
---

# Minimal Fix

Solve the requested problem with the smallest safe change that addresses the root cause.

## Workflow

1. Reproduce or verify the issue when possible.
2. Locate the responsible code path.
3. Identify the root cause before editing.
4. Determine the minimum change necessary.
5. Implement only that change plus directly necessary tests.
6. Run focused validation.
7. Review the final diff for accidental scope expansion.

## Constraints

Do not, unless strictly required:

- redesign architecture;
- rename unrelated symbols;
- reorganize unrelated files;
- update dependencies;
- migrate frameworks;
- reformat large untouched areas;
- rewrite adjacent working code;
- introduce abstractions for hypothetical future use.

Prefer existing patterns over new infrastructure.

## Testing

- Add or update a regression test when practical.
- Prefer a focused test that fails before the fix and passes after it.
- Run the narrowest relevant validation first.

## Safety

- Preserve public behavior outside the bug being fixed.
- Preserve unrelated user changes.
- Do not commit or push unless explicitly requested.

## Output

Briefly report:

- root cause;
- minimal fix applied;
- tests/validation performed;
- anything not verified.