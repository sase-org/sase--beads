# Bead: sase-127.3 — Skip no-op fleet reprojection repaints

[Bead Pages](../README.md) / [sase-127](README.md) / sase-127.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ml](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ml.md) · **Assignee:** `sase-127.3` · **Size:** small
**Created:** 2026-09-17 16:26:28 EDT · **Closed:** 2026-09-17 18:45:30 EDT
**Plan:** [202609/agents\_tab\_flicker.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_flicker.md)

## Description

skip-noop-fleet-repaint: signature-compare fleet projection inputs and skip finalize/repaint when unchanged, preserving forced sources and genuine changes, with tests.

## Notes

[2026-09-17T22:45:30Z · sase-127.3] Implemented no-op fleet projection signature skip with forced remote-source repaint preservation; re-keyed stale closed-bead symvision whitelist entries to open sase-zr.7.1.1.4 so verification can run. Verified with just test tests/ace/tui/test_agents_fleet_refresh_laziness.py, just test tests/ace/tui/test_agents_panel_fold_mounted.py::test_mounted_clan_fold_chords_zoom_and_patch_isolation, just _lint-symvision, just fmt, just check (scoped lane escalated to full suite and passed), and sase bead epic-symbols sase-127.3 (no entries).

## Dependencies

- **Blocks:** [sase-127.4](sase-127.4.md) ◐ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-127.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-127.3/README.md) | [sase-127.3](sase-127.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5b7c455`](https://github.com/sase-org/sase/commit/5b7c4553ccc7ce862535435735785ebb440ed02b) | fix(tui): skip unchanged fleet reprojections | [sase-127.3](sase-127.3.md) | 2026-09-17 19:30:36 EDT |
