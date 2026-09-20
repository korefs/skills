---
name: wire-api
description: "Connect existing frontend components to an implemented API service while preserving the current visual design and handling real interaction states."
---

# Wire API

Connect frontend components to an existing API service.

## Workflow

1. Inspect each target component.
2. Inspect the API service and request/response types.
3. Preserve the current visual implementation.
4. Connect component state and user actions to the service.
5. Handle request construction, loading, success, validation, backend errors, and navigation/state changes already implied by the feature.
6. Reuse existing error, toast, state, and navigation conventions.

## Rules

Do not redesign the component. Do not duplicate service calls already exposed through a suitable abstraction. Avoid transport details directly in templates/components when the project has a service layer. Prevent duplicate requests where relevant. Follow existing subscription/lifecycle patterns. Do not invent backend behavior.

## Validation

Run focused tests and type/lint checks when available.

## Output

Summarize components wired, endpoints used, states handled, validation performed, and unresolved ambiguities.
