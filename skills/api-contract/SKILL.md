---
name: api-contract
description: "Analyze selected OpenAPI or Swagger endpoints and map their requests, responses, errors, auth requirements, and existing frontend conventions before implementation."
---

# API Contract Analysis

Analyze a Swagger/OpenAPI contract before frontend service implementation.

## Workflow

1. Read the contract and locate requested endpoints.
2. Extract HTTP method, route, request body, path/query parameters, required fields, response schemas, status codes, error schemas, security requirements, and relevant headers.
3. Search the frontend codebase for existing equivalent services, HTTP wrappers, interceptors, base URL handling, DTO/model conventions, auth/token handling, error handling, and Observable/Promise conventions.
4. Identify reusable existing code before proposing anything new.

## Rules

Treat the contract as the primary API source of truth. Do not invent undocumented fields or endpoints. Prefer existing codebase conventions over personal preference. Explicitly call out ambiguity. Do not implement unless requested or orchestrated by a higher-level integration skill.

## Output

For each endpoint summarize method/path, request, response, known errors, auth, related frontend patterns, and implementation notes.
