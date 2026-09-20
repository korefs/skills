---
name: frontend-feature
description: "Orchestrate a complete frontend design implementation workflow including implementation, responsive review, UI states, accessibility, QA, tests, and regression checks."
---

# Frontend Feature

Orchestrate a complete frontend implementation from visual reference to reviewed implementation.

## Inputs

Expect some combination of target component/page path, desktop reference, mobile reference, feature/design spec, and repository constraints.

## Workflow

1. Inspect target files, nearby components, shared primitives, styling conventions, tests, and repository instructions.
2. Implement or update the UI following the same principles as `implement-design`.
3. Perform a responsive pass.
4. Review loading, error, empty, disabled, validation, and other relevant UI states.
5. Perform a practical accessibility pass.
6. Perform frontend QA covering visual fidelity, interaction, responsiveness, code quality, and regression risk.
7. Add or update meaningful focused tests when appropriate.
8. Perform a regression check on shared components, styles, and consumers touched by the change.

## Rules

Do not redesign beyond supplied requirements. Do not change unrelated business logic. Prefer repository-native components and patterns. Keep the change scoped. Never claim browser verification unless it was actually performed.

## Output

Provide a compact implementation summary, QA findings fixed, validation run, and remaining limitations or design ambiguities.
