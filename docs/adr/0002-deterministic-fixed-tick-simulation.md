# Deterministic fixed-tick simulation, separate from rendering

The game runs in real time on a fixed clock of 20 Ticks per second rather than turn-based, because the constant clock is core to the genre's feel. The rules are a pure, deterministic simulation (same Level plus same inputs per Tick gives the same outcome) with no browser dependencies; rendering and input are a thin layer on top. This makes Level logic testable, enables replays and solvability checks later, and lets the same rules ship inside a future desktop or mobile wrapper.

## Considered Options

- **Turn-based** (world moves only when the Guy moves): simpler and more forgiving, but plays like a different genre.
- **Variable-timestep game loop**: common in engines, but non-deterministic and hard to test.
