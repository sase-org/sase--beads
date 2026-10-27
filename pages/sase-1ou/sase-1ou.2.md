# Bead: sase-1ou.2 — Stop the ToolRun store failing with "database is locked" under parallel load (sase-18t)

[Bead Pages](../README.md) / [sase-1ou](README.md) / sase-1ou.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1oh.land--1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1oh.land.md) · **Assignee:** `sase-1ou.2` · **Size:** large
**Created:** 2026-10-27 09:20:59 EDT
**Plan:** [202610/backlog\_epic\_2\_top\_five\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202610/backlog_epic_2_top_five_task_beads.md)

## Description

toolrun-busy: identify which sase-core ToolRun store transactions hold the SQLite write lock while launcher, settle and show paths read it, fix the contention at its source in sase-core with a principled busy policy, move the core pin, retire the tests/tool/ baseline entries with fixed-at, and close sase-18t.

## Dependencies

- **Depends on:** [sase-1ou.1](sase-1ou.1.md) ✓ · ⧖ 2026-10-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ou.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.2.md) | [sase-1ou.2](sase-1ou.2.md) | 0 |
