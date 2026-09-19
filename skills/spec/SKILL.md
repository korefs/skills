---
name: spec
description: Turn a feature or technical request into an implementation-ready engineering specification grounded in the current repository. Use before substantial implementation work when the user wants a plan, technical spec, acceptance criteria, or design proposal.
---

# Engineering Spec

Create a concise, implementation-ready specification based on the request and the existing codebase.

## Workflow

1. Understand the requested outcome.
2. Inspect the repository areas that currently own the behavior.
3. Identify existing architecture and conventions that constrain the design.
4. Define the desired behavior and clear non-goals.
5. Propose the smallest architecture that fits existing patterns.
6. Identify files/components likely to change.
7. Cover important edge cases, failure modes, compatibility concerns, and migration needs.
8. Define a test strategy.
9. Write concrete acceptance criteria.
10. Call out unresolved decisions only when they genuinely block a reliable design.

## Principles

- Ground the spec in the actual repository.
- Prefer extending existing patterns over inventing parallel systems.
- Avoid premature abstractions.
- Do not silently expand product scope.
- Be explicit about assumptions.
- Separate requirements from implementation suggestions.

## Default structure

```text
# <Feature name>

## Goal

## Context / current behavior

## Desired behavior

## Non-goals

## Proposed design

## Components / files affected

## Data and contracts

## Error handling and edge cases

## Compatibility / migration

## Testing strategy

## Implementation plan

## Acceptance criteria

## Open questions
```

Omit irrelevant sections.

## File behavior

If the user asks to save the specification, prefer an existing repository convention such as `docs/`, `specs/`, or `.agents/`. If no convention exists, use `docs/specs/<descriptive-slug>.md` unless the user specifies another path.

Do not implement the feature as part of this skill unless explicitly asked.