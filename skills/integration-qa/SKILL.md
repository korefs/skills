---
name: integration-qa
description: "Audit an end-to-end frontend-to-service integration flow from user interaction through API service, response handling, UI state, and navigation."
---

# Integration QA

Review the complete frontend-to-service flow for a feature.

## Trace

Follow:

```text
UI
↓
user action
↓
component state
↓
service
↓
HTTP request
↓
response/error
↓
state update
↓
UI feedback/navigation
```

## Check

Verify the correct endpoint, request construction, loading behavior, duplicate-action prevention, success behavior, error presentation, navigation/state transitions, session/token effects when relevant, post-failure usability, and shared-state consistency.

## Execution

When browser/e2e tooling is available and configured, exercise the relevant flow and record what was actually tested. Otherwise perform static trace analysis and focused automated tests, and explicitly state that full browser verification was not performed.

## Rules

Never claim an end-to-end flow passed unless it was actually executed. Keep findings tied to observable behavior and avoid unrelated refactors.

## Output

Report flow reviewed, execution level, findings, tests run, and remaining manual verification.
