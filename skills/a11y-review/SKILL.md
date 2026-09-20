---
name: a11y-review
description: "Review the target frontend implementation for practical accessibility issues and apply focused fixes when requested."
---

# Accessibility Review

Perform a practical accessibility review of the target frontend feature.

## Check

- semantic HTML;
- accessible names;
- form labels and descriptions;
- heading hierarchy;
- keyboard navigation;
- focus order;
- visible focus state;
- buttons versus clickable divs;
- links versus buttons;
- alt text;
- ARIA only where necessary;
- validation and error announcements;
- modal/dialog focus behavior;
- obvious contrast concerns;
- touch target usability;
- disabled control semantics.

## Rules

Prefer native HTML semantics over ARIA. Do not add ARIA that duplicates native behavior. Preserve product behavior and existing repository accessibility conventions. Avoid claiming WCAG compliance unless actually verified.

## Validation

Run existing accessibility lint/tests when available.

## Output

Report concrete issues, affected elements/files, fixes applied if requested, and limitations that require browser or manual testing.
