# Bead: sase-ns.6.6.4 — Deflake the supervisor idle-timeout no-hang bound (sase-nd)

[Bead Pages](../README.md) / [sase-ns.6.6](sase-ns.6.6.md) / sase-ns.6.6.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.6.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.6.land.md) · **Assignee:** `sase-ns.6.6.4` · **Size:** large
**Created:** 2026-08-17 04:03:11 EDT
**Plan:** [202608/backlog\_top5\_gates\_green.md](https://github.com/sase-org/sase--plans/blob/main/202608/backlog_top5_gates_green.md)

## Description

monitor_idle_bound: root-cause and fix tests/monitor/test_monitor_supervise.py::test_run_supervisor_idle_timeout_fires_after_output_stalls exceeding its 5.0s `_NO_HANG_TIMEOUT` under a contended full parallel lane, without weakening the idle-timeout contract the test asserts.

## Dependencies

- **Depends on:** [sase-ns.6.6.1](sase-ns.6.6.1.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ns.6.6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ns.6.6.4/README.md) | [sase-ns.6.6.4](sase-ns.6.6.4.md) | 0 |
