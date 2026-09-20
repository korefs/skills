---
name: ui-states-review
description: "Review a frontend feature for missing loading, success, error, validation, empty, disabled, and edge-case UI states."
---

# UI States Review

Review the target UI for states that may be absent from the happy-path design.

## Inspect for

- initial state;
- loading;
- success;
- empty results;
- validation errors;
- backend errors;
- network failure;
- disabled actions;
- repeated submission;
- partial data;
- long text;
- missing optional fields;
- unavailable actions;
- stale data;
- optimistic updates where relevant.

## Forms

Verify required-field validation, invalid-field presentation, submit loading/disabled behavior, duplicate-submit prevention, server-side errors, reset behavior, and successful completion behavior.

## Data-driven screens

Verify loading UI, no-data state, error state, retry behavior when appropriate, and partial/malformed data handling.

## Rules

Do not invent product behavior unsupported by the codebase or specification. Prefer existing loaders, alerts, toasts, empty states, validation patterns, and error components.

## Output

List states already covered, missing or weak states, fixes applied if requested, and remaining product decisions.
