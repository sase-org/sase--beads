# Bead: sase-1vy.4 — Stale index-lock recovery flake under loaded scoped check (sase-1kr)

[Bead Pages](../README.md) / [sase-1vy](README.md) / sase-1vy.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1vn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vn.land.md) · **Assignee:** `sase-1vy.4` · **Size:** large
**Created:** 2026-11-28 03:14:45 EST
**Plan:** [202611/backlog\_epic\_2.md](https://github.com/sase-org/sase--plans/blob/main/202611/backlog_epic_2.md)

## Description

index-lock-flake: fix sase-1kr. Read sase-1kr and all of its notes first (7 corroborations; pairs with sase-1s4, a test that leaves a stale lock in a real checkout). Make test_run_workspace_git_command_recovers_stale_index_lock robust under the loaded scoped lane, or fix the product recovery path it guards if the flake exposes a real race. Do not close on a single green rerun; show the node green across repeated loaded runs. Run sase tool run check, then close sase-1kr and the phase bead.

## Dependencies

- **Depends on:** [sase-1vy.3](sase-1vy.3.md) ✓ · ⧖ 2026-11-28
- **Blocks:** [sase-1vy.5](sase-1vy.5.md) ◐ · ⧖ 2026-11-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vy.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vy.4/README.md) | [sase-1vy.4](sase-1vy.4.md) | 0 |
