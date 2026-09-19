---
name: ship
description: Perform a final pre-ship engineering pass on the current change: inspect the diff, remove accidental leftovers, run appropriate validation, check regression/security basics, and prepare commit and PR text. Use when implementation is believed complete and the user wants it ready to hand off or merge. Do not push or merge automatically.
---

# Ship

Prepare the current work for review/merge without silently publishing it.

This is a finalization workflow, not an excuse to redesign completed work.

## Workflow

### 1. Understand the final change

- Inspect `git status`.
- Inspect the complete relevant diff against the likely base branch.
- Read enough surrounding code to understand the intended behavior.

### 2. Remove accidental leftovers

Check the changed files for:

- debug logs/prints;
- temporary flags;
- hardcoded test values;
- secrets/credentials;
- commented-out experiments;
- generated artifacts that should not be committed;
- accidental TODO/FIXME markers introduced during the task;
- unused imports/variables;
- obviously dead code created by the change.

Only remove items that are clearly accidental. Do not perform unrelated cleanup.

### 3. Review for correctness

Perform a focused final review for:

- correctness;
- error handling;
- regression risks;
- API/schema/config compatibility;
- security basics;
- performance mistakes;
- missing tests.

Fix clear in-scope issues found during this pass.

### 4. Validate

Determine and run the repository-native relevant checks, such as:

- formatter/check-format;
- linter;
- type checker;
- focused tests;
- broader test suite when reasonable;
- build;
- relevant integration/smoke tests.

Start focused and expand appropriately.

Never claim a check passed unless it was actually run.

### 5. Final diff review

Review the final diff again after fixes and validation.

Ensure:

- changes are coherent;
- unrelated files are not included;
- no user work was overwritten;
- behavior matches the requested task/spec.

### 6. Prepare delivery text

Generate:

1. a Conventional Commit message based on the final intended commit contents;
2. a PR title;
3. a concise PR description containing summary, meaningful changes, and validation.

## Commit behavior

Do not create a commit by default as part of `ship`; prepare the work and commit text. If the user explicitly asks `ship and commit`, create a local commit after all checks pass.

## Safety

Never automatically:

- push;
- force-push;
- merge;
- rebase;
- publish packages;
- deploy;
- create releases;
- discard unrelated changes.

These require an explicit user request.

## Output

Use a compact final report:

```text
## Ready state
- ...

## Validation
- ...

## Commit
<commit message>

## PR
<title>

<description>

## Remaining notes
- ...
```

Omit empty sections.