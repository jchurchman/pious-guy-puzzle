# TypeScript

- No `any`. Use `unknown` when a type is genuinely uncertain.
- Interfaces for object shapes; `type` aliases for unions, intersections, and utility types.
- Avoid non-null assertions (`!`) unless surrounding logic guarantees the value.
- Do not use TS `enum` or string-literal unions for fixed sets (Tile kinds, Key colors, Timer
  Modes, Death reasons). Use a `const` object plus a `ValueOf` type (from `src/types/utility`):

  ```ts
  export const TIMER_MODE = {
    CASUAL: 'casual',
    COUNTDOWN: 'countdown',
  } as const;

  export type TimerMode = ValueOf<typeof TIMER_MODE>;
  ```

- Types used by more than one module live in `src/types/`.
- Absolute imports start at the repository root, e.g. `src/rules/game` (see
  [general.md](general.md) for import rules). `tsconfig.json` and the Vite config resolve
  `src/…` paths, and the ESLint import-sort groups treat `src/` as internal; keep the three in
  step.
