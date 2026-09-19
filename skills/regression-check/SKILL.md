---
name: regression-check
description: Analyze the current changes for unintended behavior regressions by comparing old and new behavior, tracing affected consumers, and running relevant validation. Use after implementations, fixes, or refactors. Read-only unless explicitly asked to repair issues.
---

# Regression Check

Look specifically for things the current change may have unintentionally broken.

## Workflow

1. Inspect the complete relevant diff.
2. Understand the previous behavior from the base revision or pre-change implementation.
3. Identify changed contracts, branches, side effects, schemas, defaults, timing, error behavior, and dependencies.
4. Find direct and indirect consumers of the changed code.
5. Evaluate likely regression scenarios.
6. Inspect existing tests and identify gaps.
7. Run relevant tests/build/type-check/lint checks when available.
8. Report only plausible regressions supported by evidence.

## Areas to inspect

Depending on the codebase, consider:

- API compatibility;
- persisted data/schema compatibility;
- null/default behavior;
- serialization/deserialization;
- error/status-code behavior;
- authentication/authorization;
- caching and invalidation;
- retries/idempotency;
- concurrency;
- cleanup/resource lifecycle;
- UI loading/error/empty states;
- mobile/responsive behavior;
- performance-sensitive loops/queries;
- configuration/environment handling.

## Output

Use this structure:

```text
## Regression risks

### <severity> — <short title>
- Evidence:
- Previous behavior:
- New behavior:
- Impact:
- Suggested verification/fix:

## Validation performed
- ...
```

If no material regression is found, say so clearly and list what was checked.

## Safety

Read-only unless the user explicitly asks to fix the issues.