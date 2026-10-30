# Bead: sase-1pu.5 — Publish terminal agent-run state instead of leaving thousands of rows active (sase-1cc)

[Bead Pages](../README.md) / [sase-1pu](README.md) / sase-1pu.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pn.land.md) · **Assignee:** `sase-1pu.5` · **Size:** large
**Created:** 2026-10-29 19:19:01 EDT
**Plan:** [202610/task\_backlog\_epic\_3.md](https://github.com/sase-org/sase--plans/blob/main/202610/task_backlog_epic_3.md)

## Description

published-run-state-freshness: ensure a completed or failed run in a published hood eventually updates the agents-sidecar state snapshot. Choose a reliable terminal-publication or reconciliation path, account for concurrent hood publication, and provide a safe bounded backfill plan for existing stale rows. Verify terminal-state convergence and that live runs are not marked terminal.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pu.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.5.md) | [sase-1pu.5](sase-1pu.5.md) | 0 |
