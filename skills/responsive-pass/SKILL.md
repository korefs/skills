---
name: responsive-pass
description: "Review and fix responsive frontend behavior across common viewport sizes without redesigning the feature or changing unrelated behavior."
---

# Responsive Pass

Perform a focused responsive-layout review of the target frontend implementation.

## Workflow

1. Inspect the target component and its containing layout.
2. Identify fixed widths, heights, offsets, grids, flex layouts, text constraints, and media that may fail responsively.
3. Review representative widths such as 320, 375, 390, 430, 768, 1024, and 1440+ pixels when tooling allows.
4. Compare against supplied mobile and desktop references when available.
5. Fix only concrete responsive issues.

## Check for

- horizontal overflow;
- clipped content;
- fixed dimensions that break on smaller screens;
- unusable controls or touch targets;
- broken flex/grid wrapping;
- text truncation;
- poor spacing;
- oversized or undersized media;
- modal/dialog overflow;
- forms that become too wide or narrow;
- desktop-only assumptions;
- confusing mobile content order.

## Rules

Preserve the intended design. Prefer existing breakpoints and content-driven layout over viewport-specific hacks. Do not change unrelated business logic or unrelated pages.

## Output

Report issues found, responsive fixes applied, affected breakpoints, validation performed, and remaining limitations.
