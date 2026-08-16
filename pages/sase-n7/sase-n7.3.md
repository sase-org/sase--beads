# Bead: sase-n7.3 — Stop the O(archive) index query

[Bead Pages](../README.md) / [sase-n7](README.md) / sase-n7.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03q](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03q.md) · **Assignee:** `sase-n7.3` · **Size:** medium
**Created:** 2026-08-16 11:17:11 EDT
**Plan:** [202608/tui\_startup\_monitor\_reconcile.md](https://github.com/sase-org/sase--plans/blob/main/202608/tui_startup_monitor_reconcile.md)

## Description

bounded-query: give reconciliation its own bounded artifact-index query instead of the unbounded full-history `include_hidden` scan of the 115 MB index, leave the `list_monitors` listing path unchanged, and pin the new bounds with a test. Escalate to the Rust core if the predicate is not expressible in the existing wire query.

## Dependencies

- **Blocks:** [sase-n7.4](sase-n7.4.md) ◐ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n7.3/README.md) | [sase-n7.3](sase-n7.3.md) | 0 |
