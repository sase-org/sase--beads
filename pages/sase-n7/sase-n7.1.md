# Bead: sase-n7.1 — Reorder the reconcile guards

[Bead Pages](../README.md) / [sase-n7](README.md) / sase-n7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03q](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03q.md) · **Assignee:** `sase-n7.1` · **Size:** small
**Created:** 2026-08-16 11:16:22 EDT · **Closed:** 2026-08-16 11:35:08 EDT
**Plan:** [202608/tui\_startup\_monitor\_reconcile.md](https://github.com/sase-org/sase--plans/blob/main/202608/tui_startup_monitor_reconcile.md)

## Description

guards: reorder `should_reconcile_dead_supervisor` so the cheap `monitor_state`/`pid` rejects run before `proc_shell_owns()`, which currently does a full proc-store read for all 147 records when 0 survive the next two lines; add a test asserting the proc lookup is skipped for terminal and pid-less records. Measured saving 1.47 s.

## Notes

[2026-08-16T15:35:08Z · sase-n7.1] Reordered should_reconcile_dead_supervisor guards so cheap monitor_state/pid checks run before proc_shell_owns(); added test_should_reconcile_dead_supervisor_skips_proc_lookup_for_terminal_record regression test. Verified: full reconcile test suite (7 passed) and just check (fmt, lint, mypy, symvision, scoped tests) all green after just install rebuilt the Rust extension.

## Dependencies

- **Blocks:** [sase-n7.4](sase-n7.4.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n7.1/README.md) | [sase-n7.1](sase-n7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6d9db4c`](https://github.com/sase-org/sase/commit/6d9db4c26a357c78b0b015f14e8379c6fc7d365c) | perf(monitor): skip proc-store lookup before cheap reconcile guards | [sase-n7.1](sase-n7.1.md) | 2026-08-16 11:36:42 EDT |
