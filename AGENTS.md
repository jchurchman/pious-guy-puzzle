# Pious Guy Puzzle

A real-time, tile-based browser puzzle game whose rules are a homage to the Chip's Challenge
genre, with an original skin: a guy who has had a rough life, seeking answers and enlightenment,
in a universal theme that points to no specific religion. Plain TypeScript and canvas, no game
engine, no framework.

## Read before you start

Read only the docs that match your task.

| If the task involves…                                     | Read                                                             |
| --------------------------------------------------------- | ---------------------------------------------------------------- |
| Game terms (Level, Tile, Tick, Guy, Gate, Level Code…)    | [GLOSSARY.md](GLOSSARY.md)                                       |
| Why the game is built the way it is                       | [docs/adr/](docs/adr/)                                           |
| Folder layout and stack                                   | [docs/project-structure.md](docs/project-structure.md)           |
| Setup, running, building                                  | [docs/development.md](docs/development.md)                       |
| Writing any code: principles and naming                   | [docs/conventions/general.md](docs/conventions/general.md)       |
| TypeScript                                                | [docs/conventions/typescript.md](docs/conventions/typescript.md) |
| Writing tests                                             | [docs/conventions/testing.md](docs/conventions/testing.md)       |
| Branches, commits, pull requests                          | [docs/conventions/git.md](docs/conventions/git.md)               |

## Plan Mode

- Make the plan extremely concise. Sacrifice grammar for the sake of concision.
- At the end of each plan, give me a list of unresolved questions to answer, if any.

## Verification

Run after you finish a change. Fix what it reports and re-run until it is clean.

```bash
npx eslint <files>
npx tsc --noEmit
npx prettier --check <files>
npx vitest run <test files>   # e.g. src/rules
```

## Never edit

- `.claude/settings.local.json`, `node_modules/`, and `dist/`.

## Permissions

- **Allowed without asking:** linting, type-checking, formatting, and running tests, including
  the full suites above.
- **Ask first:** installing, removing, or upgrading packages; any git operation that changes
  history or remotes (`commit`, `push`, `checkout`, `rebase`, etc.); deleting files not created
  during the current task; running a full build (`npm run build`).

## Working agreements

These apply to every task.

- If you are not sure what I meant, stop and ask one question before editing, even partway
  through a queue of work. Then resume the queue.
- Before changing anything, list every file you will need and read them in one pass. Then work
  test-first, one red-green slice at a time (see [testing.md](docs/conventions/testing.md)),
  running the relevant tests after each slice and the full verification at the end.
- Before writing "we do X" or "we don't have X" anywhere, reopen the code and cite `file:line`.
- Stop at each PR boundary and wait for my review before starting the next PR.
- Treat work as a queue. When I propose tweaks or corrections mid-task, append them to the queue
  instead of jumping to them. Stop only when the queue is empty.
- You Aren't Gonna Need It. Never expand scope without permission. Suggest scope improvements
  when they make sense, but do not act on them unasked. Every change must be justifiable.
- This project is an early prototype: favor simple, working code over production hardening,
  except for the determinism of the rules (ADR-0002). The same Level and the same inputs must
  always produce the same outcome.
- Keep changes as narrow as the request. If you find tangential issues (e.g. code that breaks
  conventions), list them in your summary and offer to add TODO comments at those spots.

## Agent skills

### Issue tracker

Issues are tracked in GitHub Issues on `jchurchman/pious-guy-puzzle` via the `gh` CLI. See
`docs/agents/issue-tracker.md`.

### Domain docs

Single-context: one `GLOSSARY.md` and `docs/adr/` at the repo root (created lazily). See
`docs/agents/domain.md`.
