# Bead: sase-7s.3 — Updates tab split and Agent CLIs sub-tab

[Bead Pages](../README.md) / [sase-7s](README.md) / sase-7s.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-7s.3`
**Created:** 2026-07-19 23:42:52 UTC
**Plan:** [202607/agent\_cli\_updates.md](https://github.com/sase-org/sase--plans/blob/main/202607/agent_cli_updates.md)

## Description

'Updates tab split and Agent CLIs sub-tab' section: split the Admin Center Updates tab into Core / Plugins / Agent CLIs sub-tabs, add the new Agent CLIs master/detail browser with granular update marks, bind the pane-wide `A` (update agent CLIs) keymap, and refresh docs, hints, help modal, and visual snapshots.

## Notes

Implemented the Updates tab split into Core, Plugins, and Agent CLIs; added the Agent CLI master/detail browser, granular marking and pane-wide update action, tracked/deduplicated execution, status/outcome refresh, help/docs, tests, and PNG snapshots. Validation: SASE_PYTEST_WORKERS=8 just check passed.

## Dependencies

- **Depends on:** [sase-7s.1](sase-7s.1.md) ✓
- **Blocks:** [sase-7s.4](sase-7s.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-7s.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-7s.3/README.md) | [sase-7s.3](sase-7s.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`1afba63`](https://github.com/sase-org/sase/commit/1afba633d9bfe27bdfbb3fe7598b2d577d51b16f) | feat(tui): add agent CLI update browser (sase-7s.3) | [sase-7s.3](sase-7s.3.md) | 2026-07-20 01:51:22 |
