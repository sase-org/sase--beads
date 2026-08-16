# Bead: sase-n7.2 — Kill the N+1 proc-store reads

[Bead Pages](../README.md) / [sase-n7](README.md) / sase-n7.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03q](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03q.md) · **Assignee:** `sase-n7.2` · **Size:** medium
**Created:** 2026-08-16 11:16:45 EDT
**Plan:** [202608/tui\_startup\_monitor\_reconcile.md](https://github.com/sase-org/sase--plans/blob/main/202608/tui_startup_monitor_reconcile.md)

## Description

snapshot: add a snapshot-scoped proc lookup so `get_proc` stops re-reading and re-parsing the whole store per id, thread one snapshot through the reconcile pass and `_with_proc_projection`, and test that proc-store reads stay bounded regardless of record count.

## Dependencies

- **Blocks:** [sase-n7.4](sase-n7.4.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n7.2/README.md) | [sase-n7.2](sase-n7.2.md) | 0 |
