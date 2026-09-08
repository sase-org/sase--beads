# Bead: sase-xe.16.9 — Fleet benches under faults and the remaining failure-table tests

[Bead Pages](../README.md) / [sase-xe.16](sase-xe.16.md) / sase-xe.16.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08c.md) · **Assignee:** `sase-xe.16.9` · **Size:** large
**Created:** 2026-09-08 10:21:39 EDT
**Plan:** [202609/remote\_dispatch\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_completion.md)

## Description

fleet-perf-faults: extend the j/k agents bench suite with fleet scenarios - a hung host, a reconnect storm, and an event burst - assert the p95 < 16 ms performance contract, and document the capture recipe in the perf runbook. Add the two failure-table fault tests still missing after landing: a host hang hits the facade deadline and leaves other hosts unaffected, and name/PID reuse is rejected by exact-instance fencing on remote rows. Wire or deliberately defer explicit-follow family promotion at reconciliation time (the follow store's reconcile path accepts promotions, but no production caller computes them from followed-batch family identity).

## Dependencies

- **Depends on:** [sase-xe.16.7](sase-xe.16.7.md) ✓ · ⧖ 2026-09-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.9/README.md) | [sase-xe.16.9](sase-xe.16.9.md) | 0 |
