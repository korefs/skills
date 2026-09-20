---
name: integrate-api
description: "Orchestrate a complete frontend API integration from contract analysis through service implementation, component wiring, state review, contract QA, tests, and integration QA."
---

# Integrate API

Orchestrate a complete frontend-to-backend integration workflow.

## Inputs

Expect a Swagger/OpenAPI source, relevant routes/endpoints, target frontend components, and optionally a reference service.

## Workflow

1. Analyze contract methods, routes, requests, responses, errors, and auth.
2. Inspect the codebase for existing services, equivalent endpoints, API clients, interceptors, models, error handling, state conventions, and supplied references.
3. Implement or update the service layer and required types using repository conventions.
4. Wire target components without redesigning them.
5. Review loading, success, errors, duplicate submissions, lifecycle, and edge cases.
6. Run contract QA against the final implementation.
7. Add or update focused tests where practical.
8. Trace or execute the end-to-end frontend-to-service flow.
9. Perform regression checks on shared services, interceptors, auth state, or reusable components touched by the change.

## Rules

Prefer existing code over parallel implementations. Do not invent contract behavior. Preserve the existing UI unless integration requires a state-related adjustment. Do not change unrelated endpoints. Keep architecture consistent with the repository.

## Output

Report endpoints implemented, components wired, QA findings fixed, tests/validation run, and remaining limitations.
