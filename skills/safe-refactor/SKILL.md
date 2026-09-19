---
name: safe-refactor
description: Improve the structure, readability, duplication, or maintainability of existing code while preserving externally observable behavior. Use when the user asks for a refactor that should not change functionality.
---

# Safe Refactor

Refactor conservatively while preserving behavior.

## Workflow

1. Define the exact refactor scope.
2. Inspect callers, consumers, interfaces, tests, and relevant runtime assumptions.
3. Identify existing tests that protect current behavior.
4. Run focused baseline tests when practical.
5. Refactor incrementally.
6. Avoid mixing behavior changes with structural changes.
7. Run formatter/linter/tests/build checks relevant to the touched area.
8. Review the final diff specifically for behavioral changes.

## Allowed goals

Examples include:

- simplify control flow;
- reduce duplication;
- improve naming;
- extract cohesive functions/classes;
- improve separation of concerns;
- remove dead code proven to be unused;
- make types/contracts clearer;
- reduce unnecessary complexity.

## Constraints

- Preserve public APIs unless changing them is explicitly requested.
- Preserve serialization formats, database behavior, error semantics, and externally observable side effects.
- Do not introduce a new framework or dependency just to refactor.
- Avoid speculative abstractions.
- Do not reformat unrelated files.
- Do not combine unrelated cleanup with the requested refactor.

## Validation

If behavior is insufficiently covered, add characterization tests before risky structural changes when practical.

## Output

Report:

- what was structurally improved;
- why behavior should remain equivalent;
- validation performed;
- any behavior-preservation risk that remains.