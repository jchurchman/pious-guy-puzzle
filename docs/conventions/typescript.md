# TypeScript

- No `any`. Use `unknown` when a type is genuinely uncertain.
- Interfaces for object shapes; `type` aliases for unions, intersections, and utility types.
- Avoid non-null assertions (`!`) unless surrounding logic guarantees the value.
- Do not use TS `enum` or string-literal unions for fixed sets (Tile kinds, Key colors, Timer
  Modes, Death reasons). Use a `const` object plus a `ValueOf` type (from `@/types/utility`):

  ```ts
  export const TIMER_MODE = {
    CASUAL: 'casual',
    COUNTDOWN: 'countdown',
  } as const;

  export type TimerMode = ValueOf<typeof TIMER_MODE>;
  ```

- Types used by more than one module live in `src/types/`.
- The `@/` alias maps to `src` (see [general.md](general.md) for import rules). It is defined in
  the Vite config and `tsconfig.json`. Keep the ESLint import-sort groups in step when aliases
  change.
