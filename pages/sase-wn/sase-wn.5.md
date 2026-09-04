# Bead: sase-wn.5 — Per-surface change tokens for ace auto-refresh

[Bead Pages](../README.md) / [sase-wn](README.md) / sase-wn.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.o.f0` · **Assignee:** `sase-wn.5` · **Size:** large
**Created:** 2026-09-04 12:11:07 EDT
**Plan:** [202609/sase\_idle\_cpu\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_idle_cpu_diet.md)

## Description

ace-refresh-tokens: replace ace's unconditional full reconcile every refresh_interval with cheap per-surface change tokens (agents, axe, notifications, patches, procs) that work without an fs watcher, restoring the dirty-gate design on macOS and under Linux churn, with a periodic full-sanity reconcile and a sunset flag keeping the old unconditional path reachable.

## Dependencies

- **Blocks:** [sase-wn.10](sase-wn.10.md) ◐ · ⧖ 2026-09-04
- **Blocks:** [sase-wn.6](sase-wn.6.md) ◐ · ⧖ 2026-09-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wn.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-wn.5.md) | [sase-wn.5](sase-wn.5.md) | 0 |
