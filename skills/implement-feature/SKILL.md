---
name: implement-feature
description: "Orchestrate a complete feature implementation across frontend design, API integration, QA, tests, regression review, and final ship readiness."
---

# Implement Feature

Orchestrate a complete feature implementation that may include visual frontend work and backend-service integration.

## Inputs

Expect some combination of design references, target component/page, feature spec, OpenAPI/Swagger contract, endpoint list, reference service, and acceptance criteria.

## Workflow

1. Understand scope by inspecting repository instructions, feature spec, design references, target files, API contract, and related code.
2. If visual work is required, create/update the UI and implement responsive behavior.
3. If service work is required, analyze the contract, implement/reuse service infrastructure, wire components, and handle runtime states.
4. Run relevant quality passes: responsive review, UI states review, accessibility review, contract QA, integration QA, and frontend QA.
5. Add/update meaningful tests.
6. Perform regression review across shared components, services, state, routes, contracts, and consumers.
7. Perform final ship-readiness cleanup and repository-native validation.

## Rules

Do not invent requirements absent from the design, spec, contract, or codebase. Prefer existing architecture and shared abstractions. Keep unrelated changes out of scope. Do not push, merge, deploy, or publish automatically. Never claim browser/e2e verification unless actually executed.

## Output

Report implemented scope, files/areas changed, QA performed, tests/validation run, unresolved issues, and final readiness state.
