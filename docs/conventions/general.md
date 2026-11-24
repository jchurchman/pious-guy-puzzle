# General conventions

## Principles

- Prefer pure functions. A function is pure if any call to it could be replaced by its return
  value without changing what the program does.
- Do not mutate arguments or shared state; return new values. Advancing the game one Tick returns
  a new game state rather than changing the old one.
- Keep side effects (the real-time loop, keyboard input, drawing, storage, timers) in a thin outer
  layer: the shell. The rules and progression take their inputs as arguments and never touch the
  browser (ADR-0002).
- A function's name must describe everything it does. If describing it takes "and", split it.
- Extract magic strings and magic numbers into named constants (e.g. Ticks per second, Ticks per
  move, Viewport size). Constants direct logic; text players read goes in `src/strings/`, not in
  constants. Hint messages are the exception: they live in their Level file.
- Use the [glossary](../../GLOSSARY.md) terms in code: `collectiblesRemaining`, not
  `chipsLeft`. Rule-level code never uses skin names (ADR-0001).
- ESLint enforces `complexity` (max 10), `max-depth` (max 3), and `no-nested-ternary`. Fix a
  violation by extracting a named function or returning early, not by disabling the rule.
- Do not use index barrel files. Import the file that defines what you need.
- Imports are either same-folder (`./tiles`) or absolute from the repository root
  (`src/rules/game`), never `../` and never through an alias such as `@/`. ESLint rejects both.
- Colocate code with its only consumer. Move it to a shared location (`types/`, `utils/`) only
  once a second consumer needs it.

## Naming

- Types and interfaces: `PascalCase`
- Functions and variables: `camelCase`
- Constants: `SCREAMING_SNAKE_CASE`, including the keys of enum-like objects
- Function prefixes:
  - `get…` reads a value from an object or payload, e.g. `getKeyCount`
  - `aToB` transforms one shape into another, e.g. `levelTextToLevel`
  - `make…` is a factory that returns a function or configured instance
  - `create…` builds a new object, e.g. a new game or initial progress
- `get…` functions only read. They never write, draw, or touch storage.
