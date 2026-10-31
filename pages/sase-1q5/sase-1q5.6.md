# Bead: sase-1q5.6 — Move small synchronous work off the UI pump

[Bead Pages](../README.md) / [sase-1q5](README.md) / sase-1q5.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5k.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5k.linker.w0.md) · **Assignee:** `sase-1q5.6` · **Size:** small
**Created:** 2026-10-30 18:38:11 EDT
**Plan:** [202610/tui\_index\_lock\_speedup.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_index_lock_speedup.md)

## Description

pump-probe-trims: use one persistent malloc_trim worker, move the tool-runs token probe off the countdown tick, and debounce the prompt subtitle restyle while keeping typing and the caret immediate.

## Dependencies

- **Blocks:** [sase-1q5.7](sase-1q5.7.md) ◐ · ⧖ 2026-10-30
- **Blocks:** [sase-1q5.8](sase-1q5.8.md) ◐ · ⧖ 2026-10-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1q5.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1q5.6/README.md) | [sase-1q5.6](sase-1q5.6.md) | 0 |
