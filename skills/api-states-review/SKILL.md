---
name: api-states-review
description: "Review a frontend API integration for missing request, loading, error, retry, duplicate-submit, lifecycle, and edge-case handling."
---

# API States Review

Review a frontend API integration for runtime states and failure modes.

## Request lifecycle

Check that requests start correctly, loading begins and ends, controls disable when appropriate, duplicate submissions are prevented, and retries do not create duplicate side effects.

## Errors

Check relevant validation errors, 400 responses, auth failures, conflicts, server errors, network failures, timeouts, and malformed or partial responses.

## Success

Check state updates, navigation, notifications, form reset, token/session handling, and cache/state invalidation where relevant.

## Lifecycle

Check subscriptions/listeners cleanup, race conditions, stale responses, repeated component initialization, and cancellation when the project supports it.

## Rules

Base checks on the actual contract and code. Do not add generic handling for impossible cases. Reuse existing application patterns and keep fixes scoped.

## Output

Report covered states, missing states, concrete risks, and fixes applied if requested.
