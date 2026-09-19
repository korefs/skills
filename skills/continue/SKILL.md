---
name: continue
description: Recover the current task from repository evidence and existing handoff/spec/TODO context, determine where prior work stopped, and continue with the next logical implementation steps. Use when resuming work in a new Codex session without wanting to re-explain the project.
---

# Continue Work

Recover context from the repository and resume the unfinished task without redoing completed work.

## Context recovery order

Inspect, when present and relevant:

1. current `git status` and diff;
2. repository instruction files such as `AGENTS.md`;
3. task handoff files;
4. referenced or nearby specs;
5. task-specific TODO/checklist files;
6. recent branch commits;
7. tests and implementation around the changed area.

Do not recursively read every documentation file. Load only enough context to identify the active task and next work.

## Workflow

1. Determine the likely active task from repository evidence.
2. Reconstruct:
   - goal;
   - completed work;
   - current unfinished state;
   - validation already performed;
   - known blockers;
   - remaining acceptance criteria.
3. Verify the current code instead of blindly trusting stale notes.
4. Select the next logical incomplete step.
5. Continue implementation.
6. Add/update tests as appropriate.
7. Run relevant validation.
8. Stop only when the task is complete, genuinely blocked, or the available repository context cannot identify a safe next action.

## Rules

- Do not reimplement completed functionality.
- Do not overwrite uncommitted user changes.
- Treat handoff/spec files as context, but verify them against current code.
- Do not silently broaden scope.
- Prefer finishing an existing coherent task before unrelated cleanup.

## Output

At completion, summarize:

- context recovered;
- work continued/completed;
- validation performed;
- remaining blockers or next steps, if any.

Do not commit or push unless explicitly requested.