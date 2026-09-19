---
name: tests
description: Add or improve automated tests for the current code changes or a specified behavior using the repository's existing testing conventions. Use when the user asks to create tests, improve coverage, or protect a change with regression tests.
---

# Tests

Add high-value automated tests using the repository's established test stack and patterns.

## Workflow

1. Inspect the code/change under test.
2. Inspect nearby tests and repository test conventions.
3. Identify meaningful behaviors and failure modes.
4. Prioritize tests that protect behavior rather than implementation details.
5. Add the smallest useful set of tests.
6. Run the focused tests.
7. Run broader relevant tests when practical.

## Test priorities

Prefer coverage for:

- normal successful behavior;
- regression scenario for the current bug/change;
- important boundary conditions;
- error handling;
- authorization/security rules when relevant;
- data transformations and persistence semantics;
- concurrency/idempotency behavior when relevant.

## Rules

- Do not create meaningless coverage-only assertions.
- Do not heavily mock the exact implementation being tested when observable behavior can be tested instead.
- Reuse repository fixtures/builders/helpers when appropriate.
- Keep tests deterministic.
- Avoid arbitrary sleeps and timing-dependent assertions.
- Do not change production behavior merely to make a test pass. If production code is incorrect, report it or make only the minimal clearly necessary correction when the user requested both implementation and tests.
- Do not introduce a new test framework when an established one already exists.

## Output

Report:

- behaviors covered;
- test files changed;
- test commands executed and results;
- any important gap that remains.