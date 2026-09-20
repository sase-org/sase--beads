# Bead: sase-142.3 — Add rows in place and settle the column in one frame

[Bead Pages](../README.md) / [sase-142](README.md) / sase-142.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-13i.4.f0.f0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-13i.4.f0.f0.md) · **Assignee:** `sase-142.3` · **Size:** medium
**Created:** 2026-09-20 12:14:22 EDT
**Plan:** [202609/epic\_panel\_new\_node\_flicker.md](https://github.com/sase-org/sase--plans/blob/main/202609/epic_panel_new_node_flicker.md)

## Description

row-insert-without-blanking: give AgentList an in-place row insert to mirror try_remove_rows so an added node stops clearing and re-emitting the whole panel, and make the agent-list container width settle inside the refresh that changed the rows instead of one pump cycle later.

## Dependencies

- **Depends on:** [sase-142.1](sase-142.1.md) ✓ · ⧖ 2026-09-20
- **Depends on:** [sase-142.2](sase-142.2.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-142.4](sase-142.4.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-142.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-142.3/README.md) | [sase-142.3](sase-142.3.md) | 0 |
