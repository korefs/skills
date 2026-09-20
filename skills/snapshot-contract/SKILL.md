---
name: snapshot-contract
description: "Fetch or capture an OpenAPI or Swagger contract into a versioned local spec file for repeatable frontend integration work."
---

# Snapshot Contract

Capture an API contract from a provided Swagger/OpenAPI source into the repository.

## Sources

Accept a local JSON/YAML file, HTTP(S) OpenAPI/Swagger URL, or generated API-doc endpoint.

## Workflow

1. Inspect repository conventions for API specs/contracts.
2. Retrieve or read the contract.
3. Validate that it is recognizable OpenAPI/Swagger content.
4. Save it under the existing project convention, or default to `spec/contracts/<name>.openapi.json`.
5. Preserve meaningful schema information without unnecessary normalization.

## Rules

Do not fabricate contract fields. Do not silently convert API versions unless necessary. Do not store credentials or private tokens. Use only explicitly available authentication mechanisms.

## Output

Report source, saved path, OpenAPI/Swagger version, relevant paths discovered, and retrieval/parsing limitations.
