# Contributing

This repository is intended to be maintained primarily by autonomous agents with human oversight. The GitHub artifacts are meant to be a by-product of interacting with [Nexus](https://github.com/zenon-red/nexus), an autonomous agentic development framework.

## Required Reading Order

Before making changes:

1. Read this `CONTRIBUTING.md` fully.
2. Read `SOUL.md` for ZŌE's identity and personality spec.
3. Read [skills/zoe/SKILL.md](./skills/zoe/SKILL.md) for repository-specific guidance.

If guidance conflicts, prioritize:
1. Safety and security requirements
2. `CONTRIBUTING.md`
3. `SOUL.md` / `SKILL.md`

## Contribution Protocol

Before implementing a Nexus task:

1. Sync your fork with upstream using GitHub CLI: `gh repo sync`
2. Update your local clone from the now-synced fork: `git checkout main && git pull origin main`
3. Create a fresh task branch from the updated default branch using the pattern `<type>/<task-id>-<short-description>`.
4. Confirm the following before editing any files:
   - You are on the new task branch (not main): `git branch --show-current`
   - Working tree is clean (no uncommitted changes): `git status`
   - Branch tracks the correct remote (your fork): `git branch -vv`
   - Optional but useful: `git remote -v` (origin points to your fork)

Branch naming examples:

```text
feat/42-add-repo-links-to-claim-output
fix/38-auth-token-refresh
docs/15-update-quickstart
```

Types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`, `ci`, `build`, `perf`

## Working Principles

- Validate behavior from source code and runtime execution path before implementing changes.
- Base decisions on verified behavior, not assumptions in task or issue descriptions.
- Keep changes scoped and minimal, aligned with task intent.
- Preserve existing behavior unless a change is explicitly required.
- Keep sensitive data out of code, logs, issues, and commits.

## Validation Protocol

- Run the required repository checks listed in `SKILL.md` before opening or updating a PR.
- Include validation evidence in PR or task updates. If blocked, document what was tried and what is needed next.

## Commit and PR Quality

Use conventional commits:

```text
<type>[scope]: concise description
```

- type: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`, `ci`, `build`, `perf`, `revert`
- scope: optional and repository-specific
- description: imperative mood, no trailing period

For PRs:

1. Keep scope atomic and reviewable.
2. Explain why the change is needed, not only what changed.
3. Link related issues and tasks.
4. Send a friendly reminder to the `zoe` channel for review: `probe send message zoe "this is an example"`.
5. If implementation reveals additional work needed, report discovered tasks instead of expanding scope: `probe discover report --task <id> --project <id> --title "<text>" [--description "<text>"] [--type <type>] [--severity <sev>]`.

## License

By contributing, you agree that your or your agent's contributions are licensed under the MIT License.
