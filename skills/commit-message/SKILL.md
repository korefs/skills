---
name: commit-message
description: Generate a Conventional Commit message from the repository's current changes. Use when the user wants a commit message, semantic commit wording, or a concise description of staged or unstaged changes. Do not commit, stage, or modify files.
---

# Commit Message

Generate a high-quality Conventional Commit message based only on the actual repository changes.

## Workflow

1. Inspect repository status.
2. If staged changes exist, analyze staged changes as the primary commit contents.
3. If nothing is staged, analyze the working-tree diff.
4. Read enough surrounding code to correctly understand the intent when the diff alone is ambiguous.
5. Infer the most appropriate Conventional Commit type.
6. Infer a scope only when the repository structure or affected module makes the scope useful and obvious.
7. Generate the commit message.

## Conventional Commit types

Prefer these types:

- `feat`: new user-visible or developer-facing functionality.
- `fix`: bug fix.
- `refactor`: behavior-preserving code restructuring.
- `perf`: performance improvement.
- `test`: tests only.
- `docs`: documentation only.
- `build`: build system or dependencies.
- `ci`: CI/CD configuration.
- `chore`: maintenance that does not fit another type.

Use other Conventional Commit types only when clearly justified by repository conventions.

## Message rules

- Use imperative mood.
- Keep the subject concise, ideally <= 72 characters.
- Describe the intent of the change, not a raw list of filenames.
- Do not invent changes that are not present.
- Do not mention generated files unless they are materially relevant.
- Avoid vague subjects such as `update files`, `changes`, `misc fixes`, or `improvements`.
- Add a body only when the change needs important context that cannot fit in the subject.
- Add `BREAKING CHANGE:` only when the diff actually introduces a breaking change.

## Safety

- Do not run `git add`.
- Do not create a commit.
- Do not modify files.
- Do not push.

## Output

Return only the proposed commit message unless the user explicitly asks for explanation or alternatives.