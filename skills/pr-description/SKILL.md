---
name: pr-description
description: Generate a pull request title and description from the current branch changes relative to its likely base branch. Use when the user wants PR copy, a merge request description, or a review-ready summary. Do not create or modify the PR unless explicitly asked.
---

# PR Description

Generate accurate pull request copy from the actual branch contents.

## Workflow

1. Inspect the current branch, status, recent commits, and available remote/base branches.
2. Determine the likely base branch from repository conventions, upstream tracking, or common branches such as `main`, `master`, or `develop`.
3. Compare the current branch against the base using both commit history and diff.
4. Read relevant code when needed to understand behavior rather than merely restating filenames.
5. Identify:
   - purpose;
   - user/developer-visible behavior changes;
   - architecture or implementation changes worth mentioning;
   - tests added or updated;
   - migrations/configuration changes;
   - breaking changes;
   - known limitations or follow-ups.
6. Produce a concise title and useful review description.

## Rules

- Describe what the branch actually contains, not what its branch name suggests.
- Do not claim tests passed unless they were actually run or the repository provides verified evidence.
- Do not fabricate issue numbers, ticket links, screenshots, benchmarks, or rollout details.
- Separate implementation detail from behavior change.
- Prefer reviewer-relevant context over a commit-by-commit dump.

## Default output format

```text
<title>

## Summary
- ...

## Changes
- ...

## Validation
- ...

## Notes
- ...
```

Omit empty sections.

## Safety

- Do not push.
- Do not create the PR automatically.
- Do not edit repository files.

## Output

Return ready-to-paste PR title and description.