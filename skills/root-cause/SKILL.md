---
name: root-cause
description: Investigate a bug, failure, or unexpected behavior and identify the most evidence-supported root cause before any fix is attempted. Use for debugging analysis when the user wants to understand why something happens. Read-only by default.
---

# Root Cause Analysis

Investigate first. Do not jump directly to code changes.

## Workflow

1. Capture the exact symptom from the user, logs, tests, or repository state.
2. Identify the execution path involved.
3. Inspect relevant code, configuration, dependencies, and recent changes.
4. Reproduce the issue when feasible.
5. Form hypotheses.
6. Test hypotheses against code and available runtime evidence.
7. Eliminate unsupported explanations.
8. Identify the most evidence-supported root cause.
9. Determine the smallest reasonable fix options without applying them unless asked.

## Evidence rules

Explicitly distinguish:

- verified fact;
- strong inference;
- remaining hypothesis.

Do not present guesses as facts.

When evidence is insufficient, state what additional observation would discriminate between the remaining hypotheses.

## Output format

```text
## Symptom
...

## Evidence
- ...

## Root cause
...

## Why it happens
...

## Affected path
...

## Fix options
1. ...

## Verification
...
```

Omit sections that do not apply.

## Safety

Read-only unless the user explicitly asks for the fix to be implemented.