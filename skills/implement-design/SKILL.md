---
name: implement-design
description: "Implement or update a frontend UI from provided visual references while preserving existing behavior and following repository styling conventions."
---

# Implement Design

Implement or update a frontend interface from supplied screenshots, exported Figma frames, or design specs.

## Workflow

1. Inspect the target path and nearby components before editing.
2. Determine whether the task is an update to an existing UI or creation of a new one.
3. Treat supplied visual references as the source of truth for appearance.
4. Preserve existing behavior and business logic unless a visual requirement requires a small in-scope adjustment.
5. Reuse existing shared components, tokens, Tailwind utilities, and layout conventions.
6. Implement desktop and mobile references when both are supplied.
7. If no mobile reference exists, create a responsive mobile interpretation based on existing repository patterns and standard responsive design conventions.

## Visual rules

Match spacing, sizing, typography, alignment, colors, borders, radius, shadows, hierarchy, and positioning as closely as practical.

Prefer Tailwind when the project already uses Tailwind. Do not introduce a parallel styling system. Avoid arbitrary absolute positioning, screenshot-sized containers, and unexplained magic numbers when existing utilities or tokens can express the same design.

When multiple screenshots are provided for the same viewport,
treat them as sequential sections of the same page.

Use overlapping content to determine section continuity.

Use the overview image to understand the global composition and
the section screenshots for implementation detail.

Do not interpret each screenshot as a separate screen in these cases.

## Existing components

When modifying an existing component:
- preserve public inputs, outputs, state, and behavior;
- avoid unrelated refactors;
- do not rewrite working business logic for aesthetic reasons;
- keep existing tests passing.

## New components

When creating a new component:
- follow repository naming, folder, import, composition, and dependency-injection conventions;
- reuse existing primitives before creating new ones;
- keep the component focused on the requested visual scope.

## Validation

Inspect the final diff and run relevant formatter, lint, type, build, or focused test checks available in the repository.

## Output

Summarize what was implemented, files changed, responsive behavior added, validation performed, and any design ambiguity that required an inference.
