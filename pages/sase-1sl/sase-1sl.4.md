# Bead: sase-1sl.4 — Measured verification on athena and residual-leak attribution

[Bead Pages](../README.md) / [sase-1sl](README.md) / sase-1sl.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1c0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1c0.md) · **Assignee:** `sase-1sl.4` · **Size:** medium
**Created:** 2026-11-12 16:45:05 EST
**Plan:** [202611/capacity\_scan\_tui\_runaway.md](https://github.com/sase-org/sase--plans/blob/main/202611/capacity_scan_tui_runaway.md)

## Description

athena-soak: soak a TUI instance on athena for at least an hour under real agent load, verify CPU, rchar, RSS, GC-pause, and runner-CPU targets against the 2026-11-12 baseline, and attribute any residual RSS growth with the GC census.

## Dependencies

- **Depends on:** [sase-1sl.2](sase-1sl.2.md) ◐ · ⧖ 2026-11-12
- **Depends on:** [sase-1sl.3](sase-1sl.3.md) ✓ · ⧖ 2026-11-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sl.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sl.4/README.md) | [sase-1sl.4](sase-1sl.4.md) | 0 |
