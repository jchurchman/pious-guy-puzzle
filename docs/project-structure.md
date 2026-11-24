# Project structure

## Stack

- TypeScript, Vite (dev server and build), Vitest (tests).
- Canvas for the game; plain DOM for the side panel, settings, Level Code entry, and the
  Level-complete screen. No game engine, no UI framework.
- Later desktop and mobile builds are planned as wrappers (e.g. Tauri, Capacitor) around the
  same web build.

## Layout

Planned; the scaffold ticket creates it. Update this file whenever the layout changes.

```text
src/
  rules/         the Game: pure, deterministic simulation and Level-file parsing (ADR-0002)
  progression/   Level Sequence, Level Codes, settings, Best Times; storage port + adapters
  shell/         real-time loop, input, canvas renderer, DOM screens (thin, untested)
  strings/       text players read (except Hint messages, which live in Level files)
  types/         types shared by more than one module
levels/          plain-text Level files and their stored completion input scripts
docs/
  adr/           architecture decisions
  conventions/   coding conventions
  agents/        configuration for the agent skills
```
