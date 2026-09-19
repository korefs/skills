---
name: implement-spec
description: Implement an existing engineering specification end-to-end while preserving its requirements, following repository conventions, validating acceptance criteria, and avoiding unrelated scope. Use when the user provides or points to a spec that should now be implemented.
---

# Implement Spec

Implement the requested specification as completely as reasonably possible in the current repository.

## Workflow

1. Read the complete specification before editing.
2. Inspect the current implementation and repository conventions.
3. Translate acceptance criteria into a concrete internal implementation checklist.
4. Identify dependencies and implementation order.
5. Implement incrementally using existing architecture and patterns.
6. Add or update tests as part of the implementation.
7. Run focused validation throughout the work.
8. Run the broader relevant validation set at the end.
9. Re-read the specification and verify every acceptance criterion against the final implementation.
10. Review the final diff for unrelated changes.

## Rules

- Do not silently change requirements.
- If the repository conflicts with a suggested implementation detail but the desired behavior can still be satisfied, adapt the implementation while preserving the requirement.
- If a requirement truly cannot be completed, implement the rest and clearly document the blocker.
- Do not mark acceptance criteria as complete without evidence.
- Prefer repository-native dependencies and patterns.
- Do not perform opportunistic refactors outside the implementation scope.
- Preserve backward compatibility unless the spec explicitly changes it.

## Validation

Use the repository's own scripts and tools where available, such as:

- focused tests;
- integration tests;
- type checking;
- linting;
- formatting;
- build;
- relevant local smoke checks.

Do not claim a validation step passed if it was not run.

## Output

Report:

- what was implemented;
- acceptance criteria status;
- tests/validation and results;
- deviations from the proposed design, if any, and why;
- remaining blockers or follow-ups.

Do not commit or push unless explicitly requested.