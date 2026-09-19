---
name: blast-radius
description: Determine what code, behavior, consumers, tests, schemas, services, and integrations could be affected by changing a specified symbol, module, contract, or behavior. Use before risky changes or when the user asks what could break. Read-only.
---

# Blast Radius

Estimate the concrete impact surface of a proposed change using repository evidence.

## Workflow

1. Identify the exact target: symbol, file, API, schema, configuration, behavior, or component.
2. Find direct references and consumers.
3. Trace important indirect consumers through interfaces, dependency injection, events, routes, exports, shared models, and data contracts.
4. Identify tests that exercise the target or its consumers.
5. Inspect external boundaries such as:
   - APIs;
   - database schema/data;
   - queues/events;
   - caches;
   - configuration/environment variables;
   - serialization contracts;
   - filesystem/network protocols;
   - UI contracts.
6. Categorize impact by confidence.

## Confidence categories

- `Direct`: explicit reference or contract dependency.
- `Indirect`: verified downstream path through another component.
- `Potential`: plausible runtime/framework dependency that cannot be proven statically.

## Output

```text
## Target
...

## Direct consumers
- ...

## Indirect consumers
- ...

## External contracts
- ...

## Tests affected
- ...

## Potential hidden coupling
- ...

## Safest change strategy
- ...
```

Omit empty sections.

## Rules

- Do not exaggerate speculative impact.
- Do not modify code.
- Do not claim a consumer is affected solely because it has a similar name.