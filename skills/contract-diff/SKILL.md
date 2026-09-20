---
name: contract-diff
description: "Compare two OpenAPI or Swagger contract versions and summarize breaking, behavioral, and additive API changes relevant to the frontend."
---

# Contract Diff

Compare two versions of an OpenAPI/Swagger contract.

## Compare

- added or removed endpoints;
- HTTP method or route changes;
- request fields;
- required/optional changes;
- type changes;
- enum changes;
- response fields and types;
- status codes;
- auth/security changes;
- parameter changes;
- nullable behavior.

## Classify

Classify findings as Breaking, Behavioral, or Additive.

When possible, search the codebase for affected endpoints/fields and list impacted consumers.

## Rules

Do not overstate compatibility without inspecting actual consumers. Distinguish a contract change from confirmed application breakage.

## Output

Provide summary, breaking changes, behavioral changes, additive changes, likely frontend impact, and recommended follow-up.
