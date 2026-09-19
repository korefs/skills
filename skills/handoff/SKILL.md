---
name: handoff
description: Create a concise technical handoff that lets another Codex session or engineer continue the current work without rediscovering repository context. Use when pausing work, changing sessions, reaching context limits, or transferring a task. Read-only unless asked to save the handoff.
---

# Handoff

Produce a continuation-oriented snapshot of the current task.

## Workflow

1. Inspect current repository status and diff.
2. Inspect recent commits relevant to the current task.
3. Identify the original/current goal from available context and repository artifacts.
4. Determine what has already been implemented.
5. Identify the most relevant files, symbols, commands, tests, and architectural decisions.
6. Identify unfinished work, blockers, bugs, failed approaches, and open questions.
7. State the next concrete steps in execution order.
8. Include enough context for another capable engineer/agent to resume without retelling the whole history.

## Output structure

```text
# Handoff: <task>

## Goal

## Current state

## What has been completed

## Relevant files / symbols

## Important decisions

## Validation already performed

## Known issues / blockers

## Next steps

## Commands / notes useful for resuming
```

Omit empty sections.

## Rules

- Focus on continuation value, not a chronological diary.
- Include exact file paths and symbol names where useful.
- Include failed approaches only when they prevent repeated wasted work.
- Never claim something is complete solely because code exists; distinguish implemented from validated.
- Mention uncommitted changes when present.

## File behavior

When asked to save it, prefer an existing project convention. Otherwise use a descriptive file such as `HANDOFF.md` or `docs/handoffs/<task>.md` based on repository practices.

## Safety

Do not modify production code, commit, or push as part of the handoff.