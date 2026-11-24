# Testing

- **Vitest.** `npm test` runs every test once; for chosen files use `npx vitest run <test files>`.
  Put tests in a `__tests__` folder beside the code under test.
- **Test-first.** Write one failing test for one behaviour, make it pass, refactor, repeat. Do not
  write a batch of tests up front.
- **Test only through the two seams**, never internal data structures:
  - **The Game** (rules): start a game from Level text and a Timer Mode, advance it Tick by Tick
    with a held direction (or none), and assert on its Snapshot. Write Levels inline as small
    text grids. Level-file parsing errors are tested through this seam too.
  - **Progression**: Level Sequence, Level Codes, Timer Mode setting and its lock, Best Times,
    and the last Level reached, using the in-memory storage adapter.
- **Content check.** Every shipped Level must parse, have a unique Level Code, and be completed
  by replaying its stored input script through the Game. A Level change that breaks its script
  must update the script in the same PR.
- **Not unit-tested:** the shell (renderer, input, focus-loss pausing, the real-time loop). Keep
  it thin and verify it by running the game in a browser.
