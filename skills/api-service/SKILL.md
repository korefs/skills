---
name: api-service
description: "Implement frontend API services, DTOs, and related models from a Swagger or OpenAPI contract while following existing repository conventions."
---

# API Service

Implement frontend service-layer code from an API contract.

## Workflow

1. Analyze the relevant contract endpoints.
2. Inspect existing service conventions and any supplied reference service.
3. Search for reusable models, clients, utilities, interceptors, and equivalent endpoints.
4. Implement only service-layer pieces required by the requested feature.
5. Add or reuse request/response types according to project conventions.
6. Keep transport concerns inside the established service/client layer.

## Rules

Match existing naming, dependency injection, Observable/Promise/signals, base URL, interceptor, and error-handling patterns. Do not duplicate existing endpoints or create parallel infrastructure. Do not silently alter UI components. Do not invent undocumented contract fields.

## Validation

Run relevant type checks, tests, linting, or build checks.

## Output

Report endpoints implemented, files created/changed, reused infrastructure, contract ambiguities, and validation run.
