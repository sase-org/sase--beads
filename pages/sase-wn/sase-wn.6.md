# Bead: sase-wn.6 — Cache immutable axe status reads in ace

[Bead Pages](../README.md) / [sase-wn](README.md) / sase-wn.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.o.f0` · **Assignee:** `sase-wn.6` · **Size:** medium
**Created:** 2026-09-04 12:11:09 EDT
**Plan:** [202609/sase\_idle\_cpu\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_idle_cpu_diet.md)

## Description

ace-axe-status-cache: stop collect_axe_status_data re-parsing ~600 files per tick - cache immutable chop run records by (path, mtime), tail logs only when they grew, and collect full chop snapshots only when the Axe tab needs them.

## Dependencies

- **Depends on:** [sase-wn.5](sase-wn.5.md) ✓ · ⧖ 2026-09-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wn.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.6/README.md) | [sase-wn.6](sase-wn.6.md) | 0 |
