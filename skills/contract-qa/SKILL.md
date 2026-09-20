---
name: contract-qa
description: "Compare frontend API service implementation against the OpenAPI or Swagger contract endpoint by endpoint and identify mismatches."
---

# Contract QA

Compare the implemented frontend API integration against the source Swagger/OpenAPI contract.

## Compare

For each endpoint compare HTTP method, route, path/query parameters, request body, required fields, property names, types, nullable/optional behavior, headers, authentication, response shape, status codes, and documented errors.

Also check whether the frontend transforms fields unexpectedly, ignores required response data, assumes undocumented values, or fails to handle meaningful errors.

## Rules

Treat the contract as authoritative unless the repository contains explicit evidence of a known backend discrepancy. Report backend-contract inconsistencies separately from frontend bugs. Do not guess undocumented behavior.

## Output

Use concise endpoint-by-endpoint checks such as:

```text
POST /auth/login
✓ method
✓ path
✓ request schema
⚠ 401 response not handled
✗ frontend expects `token`, contract returns `accessToken`
```

Finish with PASS, PASS WITH FINDINGS, or FAIL.
