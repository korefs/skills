---
name: checkpoint
description: Safely checkpoint the current work by reviewing changes, running relevant validation, checking for obvious secrets or debug leftovers, and creating a local Conventional Commit. Use when the user wants to save the current repository state without pushing it.
---

# Checkpoint

Create a safe local checkpoint commit for the current work.

## Workflow

1. Inspect `git status` and relevant diffs.
2. Identify which changes belong to the current task.
3. Preserve unrelated user changes. Never reset, discard, or overwrite them.
4. Look for obvious accidental artifacts in the intended commit:
   - secrets or credentials;
   - debug prints/logging;
   - temporary files;
   - editor artifacts;
   - commented-out experiments;
   - accidental large binaries.
5. Determine the smallest relevant validation set from repository conventions and changed files.
6. Run relevant formatter/linter/tests/build checks when reasonably available.
7. If validation fails because of the current changes, do not hide the failure. Fix only when the fix is straightforward and clearly within scope; otherwise stop before committing and report it.
8. Stage only files that belong to this checkpoint. Never blindly use `git add .` when unrelated changes are present.
9. Generate a Conventional Commit message from the staged diff.
10. Create the local commit.
11. Verify final repository status.

## Commit rules

- Use Conventional Commits.
- Prefer one coherent checkpoint rather than mixing unrelated concerns.
- If the working tree clearly contains multiple unrelated tasks, do not silently combine them. Commit only the current coherent task when it can be identified safely.

## Safety

- Never push.
- Never force-push.
- Never rebase.
- Never reset or clean the working tree.
- Never commit secrets.
- Never amend an existing commit unless the user explicitly asks.

## Output

Report:

- validation performed and whether it passed;
- commit hash and commit message;
- any files intentionally left uncommitted;
- any important warning.