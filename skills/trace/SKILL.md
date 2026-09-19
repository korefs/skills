---
name: trace
description: Trace how a feature, request, event, value, or behavior flows through the codebase from entry point to final side effects. Use when the user wants to understand where something starts, where it goes, and which files or components participate. Read-only.
---

# Trace

Map an execution or data flow through the repository without changing code.

## Workflow

1. Identify the most likely entry points for the requested concept.
2. Search references, registrations, routes, dependency injection, event handlers, imports, interfaces, and configuration as appropriate.
3. Follow actual calls/data transformations through the codebase.
4. Include asynchronous boundaries, queues, network calls, persistence, caches, workers, callbacks, or UI state where relevant.
5. Stop at meaningful external boundaries or final side effects.
6. Note important alternate/error paths when they materially affect understanding.

## Rules

- Prefer verified call relationships over naming assumptions.
- If dynamic dispatch, reflection, framework magic, generated code, or runtime registration prevents certainty, explain the ambiguity.
- Do not include every helper function. Optimize for an understandable map.
- Include file paths and important symbols so the user can navigate directly.

## Output

Start with a compact flow, for example:

```text
UI action
  -> FeatureController.handle()
  -> DownloadService.start()
  -> Provider.openStream()
  -> HTTP client
  -> storage writer
```

Then explain each meaningful step with file paths and responsibilities.

End with notable alternate paths or uncertainties.

## Safety

Read-only. Do not modify files.