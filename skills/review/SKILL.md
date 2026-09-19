---
name: review
description: Perform a focused code review of the current changes or branch and report concrete correctness, regression, security, performance, maintainability, and test issues. Use when the user asks for code review. Read-only by default.
---

# Code Review

Review the current changes as a senior engineer. Optimize for finding real problems, not producing many comments.

## Scope

If staged changes exist and the user gives no other scope, review the staged diff. Otherwise review the working-tree diff or current branch relative to its likely base branch, whichever best matches the request.

## Workflow

1. Inspect status, diff, repository conventions, and relevant surrounding code.
2. Understand the intended behavior before judging implementation details.
3. Trace affected call paths when necessary.
4. Check for:
   - incorrect behavior;
   - edge cases;
   - regressions;
   - null/error handling;
   - concurrency issues;
   - data consistency problems;
   - security vulnerabilities;
   - authorization/authentication mistakes;
   - performance regressions;
   - resource leaks;
   - breaking API/schema/config changes;
   - missing or misleading tests;
   - accidental debug/dead code.
5. Verify suspected issues against surrounding code before reporting them.

## Review standard

Only report findings that are actionable and supported by evidence.

Do not flood the review with:

- subjective style preferences already handled by formatters;
- speculative micro-optimizations;
- unrelated legacy issues;
- requests to rewrite working code solely for personal preference.

## Severity

Use:

- `critical`: security/data-loss/outage-level issue.
- `high`: likely correctness or major regression issue.
- `medium`: meaningful bug or maintenance risk.
- `low`: legitimate but limited issue.

Do not inflate severity.

## Output

For each finding provide:

- severity;
- file and relevant location;
- concise problem statement;
- why it matters;
- concrete fix direction.

If no material issues are found, explicitly say so and mention what was reviewed.

## Safety

Read-only. Do not modify files unless the user explicitly asks to fix findings.