# Bead: sase-1ez.8 — Live before/after measurement on athena and follow-up capture

[Bead Pages](../README.md) / [sase-1ez](README.md) / sase-1ez.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vm](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vm.md) · **Assignee:** `sase-1ez.8` · **Size:** small
**Created:** 2026-10-02 16:45:07 EDT · **Closed:** 2026-10-02 22:06:51 EDT
**Plan:** [202610/tui\_freeze\_gc\_heap.md](https://github.com/sase-org/sase--plans/blob/main/202610/tui_freeze_gc_heap.md)

## Description

acceptance: on a TUI restarted onto the landed code, capture a busy hour plus a 4-hour RSS window. Use tools/tui_freeze_report to compare the frozen share, GC share, idle-collection pauses, RSS/swap growth, and j/k p95 against the 10.7-12.9% / 16.7%-gen-2 baseline. Record misses and the proposed tui_perf.md rule update as PROPOSED FOLLOW-UP notes.

## Notes

[2026-10-03T02:06:10Z · sase-1ez.8] PROPOSED FOLLOW-UP: live after-measurement needs TUI restarted onto landed code then busy-hour + 4h RSS capture via tools/tui_freeze_report (before: 12.31% frozen over 478s, median 2.5s, 0 GC rows; no tui_gc_pause/heartbeat rows exist yet)

[2026-10-03T02:06:21Z · sase-1ez.8] PROPOSED FOLLOW-UP: tui_perf.md memory update — (1) module snapshot caches hold one live version per path/scope never count-capped (mtime,size) history, (2) collector tuning lives only in gc_policy.py, (3) late hitches mean whole-process stops so check tui_gc_pause before blaming the watchdog stack

[2026-10-03T02:06:32Z · sase-1ez.8] PROPOSED FOLLOW-UP: 24-hour soak on restarted TUI to confirm RSS <0.5GB/4h, VmSwap ~0, total GC <3%, hitches <0.5%, zero automatic gen-2 within 2s of input, idle p95 <=500ms, j/k p95 <16ms

[2026-10-03T02:06:51Z · sase-1ez.8] acceptance partially verified: report reproduces 12.31% before-baseline on old log; 74+2+20 unit/structural tests pass; after-capture blocked on TUI restart so filed as 3 PROPOSED FOLLOW-UP notes; no epic-symbols

## Dependencies

- **Depends on:** [sase-1ez.1](sase-1ez.1.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ez.2](sase-1ez.2.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ez.3](sase-1ez.3.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ez.4](sase-1ez.4.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ez.5](sase-1ez.5.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ez.6](sase-1ez.6.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1ez.7](sase-1ez.7.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ez.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ez.8/README.md) | [sase-1ez.8](sase-1ez.8.md) | 0 |
