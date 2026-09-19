# Recommended everyday workflow

> [!IMPORTANT]
> This is what makes sense for my workflow; adapt it to yours.

A practical flow using the pack:

```text
$spec
       ↓
$implement-spec
       ↓
$review
       ↓
$regression-check
       ↓
$ship
       ↓
$checkpoint   # when you actually want the local commit
```

For bugs:

```text
$root-cause
       ↓
$minimal-fix
       ↓
$tests
       ↓
$regression-check
       ↓
$ship
```

For navigating an unfamiliar codebase:

```text
$trace <feature>
$blast-radius <symbol/behavior>
```

For long agent sessions:

```text
$checkpoint
$handoff

# New session
$continue
```

# Notes on customization

Once you use these for a while, tune them to your repositories rather than making them more generic. Good additions include:

- preferred base branch naming;
- repository-specific test/build commands;
- scopes allowed in Conventional Commits;
- PR template sections;
- forbidden dependency patterns;
- architectural constraints;
- required validations before a checkpoint or ship;
- paths that should never be edited automatically.

The best skill is usually not the biggest skill. It is the smallest repeatable instruction that removes friction from work you perform frequently.