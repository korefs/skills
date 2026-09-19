# Skills

This document provides a quick overview of every skill available in this repository.

For installation instructions, see the main [README.md](./README.md#install-all-skills-globally).

---

## Git & Workflow

### `commit-message`

Generates a Conventional Commit message based on the actual repository changes.

It inspects staged changes first and falls back to the working tree when nothing is staged. The generated message should describe only what actually changed.

**Useful when:** you finished a change and want a clean commit message without manually summarizing the diff.

---

### `checkpoint`

Creates a safe development checkpoint for the current work.

It reviews the current changes, performs relevant validations, checks for obvious problems such as secrets or broken tests, and prepares a clean commit.

**Useful when:** working through a long coding session and you want to save a known-good state before continuing.

---

### `pr-description`

Generates a pull request title and description based on the current branch and its changes relative to the base branch.

It focuses on explaining what changed, why it changed, and anything reviewers should know.

**Useful when:** a branch is ready for review and you do not want to manually summarize the implementation.

---

### `handoff`

Creates a structured summary of the current development state so another agent, developer, or future session can continue the work.

It captures relevant context such as:

* current goal
* implementation status
* important files
* decisions already made
* known issues
* remaining work
* suggested next steps

**Useful when:** switching agents, ending a long session, or continuing development later.

---

### `continue`

Recovers the current state of an existing task and determines the next logical step.

It inspects repository instructions, documentation, specs, recent commits, current changes, and other relevant context before proceeding.

**Useful when:** returning to a project or task without wanting to explain everything again.

---

### `ship`

Runs a final engineering pass before considering a change ready to ship.

It may inspect:

* current diff
* tests
* build status
* linting
* debug leftovers
* secrets
* regressions
* documentation
* commit readiness
* pull request readiness

**Useful when:** implementation is complete and you want a final quality gate.

---

## Code Quality

### `review`

Reviews the current code changes for meaningful engineering problems.

It focuses on issues such as:

* bugs
* regressions
* incorrect assumptions
* maintainability problems
* unsafe behavior
* missing edge cases

It avoids filling the review with low-value stylistic comments.

**Useful when:** you want a focused code review before committing or opening a pull request.

---

### `minimal-fix`

Fixes a problem using the smallest reasonable change.

It explicitly avoids unrelated refactors, architecture changes, dependency upgrades, renaming, or cleanup unless they are required to solve the issue.

**Useful when:** fixing bugs in production code or making surgical changes where scope must remain controlled.

---

### `safe-refactor`

Refactors existing code while preserving its external behavior.

It first understands the current implementation and its behavioral constraints, then improves structure, readability, duplication, or maintainability without introducing unnecessary functional changes.

**Useful when:** code works but needs cleanup without changing what it does.

---

### `tests`

Creates or improves tests related to the current implementation or changes.

It focuses on meaningful behavioral coverage rather than simply increasing test count.

Typical areas include:

* expected behavior
* edge cases
* regressions
* failure scenarios
* previously uncovered paths

**Useful when:** implementation is complete and you want confidence that its behavior is protected.

---

### `regression-check`

Analyzes the current changes for possible regressions.

It looks beyond the directly modified code and checks related consumers, contracts, workflows, tests, and indirect dependencies.

**Useful when:** a change touches shared code, infrastructure, APIs, or behavior used in multiple places.

---

## Investigation & Debugging

### `root-cause`

Investigates a bug or unexpected behavior before changing the code.

It separates symptoms from causes and gathers evidence before proposing a fix.

Typical output includes:

* observed symptom
* evidence
* root cause
* affected code paths
* possible fixes
* recommended minimal fix

**Useful when:** the cause of a bug is unclear and blindly modifying code would be risky.

---

### `trace`

Traces a feature, request, event, or behavior through the codebase.

It identifies how execution flows between relevant files, components, services, modules, APIs, or external systems.

Example:

```text
UI
↓
Controller
↓
Service
↓
Provider
↓
External API
```

**Useful when:** understanding unfamiliar code or locating where a behavior is actually implemented.

---

### `blast-radius`

Analyzes what could be affected by changing a specific part of the system.

It identifies things such as:

* direct consumers
* indirect consumers
* dependent services
* APIs
* schemas
* tests
* shared abstractions
* possible regressions

**Useful when:** planning a change to shared or sensitive code before touching it.

---

## Planning & Implementation

### `spec`

Creates a focused implementation specification for a feature, change, or technical task before coding begins.

A specification may contain:

* goal
* non-goals
* current behavior
* desired behavior
* architecture
* affected areas
* implementation plan
* edge cases
* testing strategy
* acceptance criteria

**Useful when:** the task is large enough that jumping directly into implementation would create unnecessary uncertainty.

---

### `implement-spec`

Implements an existing specification.

It treats the specification and its acceptance criteria as the primary requirements, while still inspecting the repository to understand existing architecture, conventions, and constraints.

It should not silently reinterpret or expand the scope of the specification.

**Useful when:** a task has already been designed and you want the agent focused on execution.

---

## Typical Workflows

### Feature Development

```text
spec
↓
implement-spec
↓
tests
↓
review
↓
regression-check
↓
ship
```

### Bug Fixing

```text
root-cause
↓
blast-radius
↓
minimal-fix
↓
tests
↓
regression-check
```

### Codebase Exploration

```text
trace
↓
blast-radius
↓
spec
```

### Long Development Session

```text
implement-spec
↓
checkpoint
↓
continue
↓
checkpoint
↓
ship
```

### Session Handoff

```text
handoff
↓
continue
```

---