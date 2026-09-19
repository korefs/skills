# Skills

My personal skills for AI coding agents.

These skills are designed to reduce repetitive prompting and provide consistent workflows for common software engineering tasks such as code review, debugging, testing, Git operations, refactoring, architecture analysis, and implementation planning.

See [SKILLS.md](./SKILLS.md) for a description of every available skill.

## Installation

> [!IMPORTANT]
> * These skills follow the open Agent Skills format and can be installed
> with the `skills` CLI on supported coding agents.
> * Replace `codex` with your agent's name.
> * See [Supported Agents](https://github.com/vercel-labs/skills?utm_source=chatgpt.com#supported-agents)

### Install all skills globally

```bash
npx skills@latest add korefs/skills \
  --skill '*' \
  --agent codex \
  --global \
  --yes
```

Short version:

```bash
npx skills@latest add korefs/skills -s '*' -a codex -g -y
```

### Multiple agents

```bash
npx skills@latest add korefs/skills \
  --skill '*' \
  --agent codex \
  --agent claude-code \
  --global
```

### Interactive installation

Browse and select which skills you want to install:

```bash
npx skills@latest add korefs/skills
```

### Install a specific skill

For example:

```bash
npx skills@latest add korefs/skills \
  --skill commit-message \
  --agent codex \
  --global
```

You can also install multiple skills:

```bash
npx skills@latest add korefs/skills \
  --skill commit-message \
  --skill review \
  --skill ship \
  --agent codex \
  --global
```

## Project-local installation

By default, skills can also be installed only for the current project.

```bash
npx skills@latest add korefs/skills \
  --skill review \
  --agent codex
```

Each skill contains its own `SKILL.md` with the instructions and metadata required by compatible coding agents.

## List Skills

See which skills are available in this repository:

```bash
npx skills@latest add korefs/skills --list
```

See installed skills:

```bash
npx skills@latest list
```

For global skills only:

```bash
npx skills@latest list --global
```

## Updating

Update installed skills to their latest versions:

```bash
npx skills@latest update
```

For globally installed Codex skills:

```bash
npx skills@latest update --global --agent codex
```

## Remove Skills

Installed skills can be removed using:

```bash
npx skills@latest remove
```

## Philosophy

The goal of this repository is not to create giant prompts that attempt to solve every possible engineering problem.

Instead, each skill should represent a small, predictable engineering capability that is useful enough to keep available at all times.

A good skill should:

- solve one recognizable problem
- minimize repeated prompting
- have clear boundaries
- avoid unnecessary changes
- inspect the actual repository before making assumptions
- preserve existing architecture unless change is required
- prefer evidence over speculation
- produce predictable results
- compose well with other skills

The idea is simple:

> If you keep giving an AI coding agent the same instruction, it probably deserves to become a skill.

## Example Workflow

A typical feature workflow might look like:

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

For debugging:

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

For understanding an unfamiliar codebase:

```text
trace
  ↓
blast-radius
  ↓
spec
```

## Contributing

This repository primarily contains opinionated engineering workflows that I use personally.

Suggestions, improvements, and pull requests are welcome as long as they preserve the core philosophy of keeping skills focused, predictable, and reusable.

When adding a new skill:

1. Create a directory under `skills/`.
2. Add a valid `SKILL.md`.
3. Give the skill a focused responsibility.
4. Avoid overlapping heavily with existing skills.
5. Prefer explicit guardrails over vague instructions.
6. Test the skill against a real repository before submitting it.

## License

MIT License.

See [LICENSE](./LICENSE) for details.