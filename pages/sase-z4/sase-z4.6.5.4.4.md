# Bead: sase-z4.6.5.4.4 — Regenerate the capacity-strip visual corpus deliberately

[Bead Pages](../README.md) / [sase-z4.6.5.4](sase-z4.6.5.4.md) / sase-z4.6.5.4.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-z4.6.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.6.5.land.md) · **Assignee:** `sase-z4.6.5.4.4` · **Size:** medium
**Created:** 2026-09-10 17:42:17 EDT · **Closed:** 2026-09-10 19:04:45 EDT
**Plan:** [202609/weighted\_capacity\_remaining\_acceptance.md](https://github.com/sase-org/sase--plans/blob/main/202609/weighted_capacity_remaining_acceptance.md)

## Description

capacity-visual-corpus: settle the capacity-strip text and regenerate the stale agents-pane PNG goldens by inspection, retiring the status-strip diff class that has kept just test-visual red since the prefix landed.

## Notes

[2026-09-10T23:03:54Z · sase-z4.6.5.4.4] PROPOSED FOLLOW-UP: residual non-capacity-strip agents-pane visual failures remain after the capacity-strip rebaseline — at HEAD 74a4e4282, after updating 90 PNGs whose HEAD-vs-working diff boxes are all confined to y=91..116/92..115/93..115 status-strip rows, the full agents-pane visual subset still reports 21 failed / 82 passed. Fresh mismatch artifacts are not strip-only: clan/tribe/family level-2 body diffs (for example agents_clan_panel_epic_level_2 bbox=(59,92)-(1437,531), agents_clan_panel_swarm_level_2 bbox=(59,92)-(1437,653), agents_tribe_panel_level_2 bbox=(59,92)-(1437,751), agents_family_conversation_level_2 bbox=(59,92)-(1437,604)); gate/monitor shell rows include timestamp/body drift to y=208; fleet has a missing "0 results" hard assertion plus a large keyboard-focus body diff; agents_task_bead_notes and agents_metadata_zoom_modal have body-only diffs; agents_external_repo_diff_file_panel now has a right-edge non-strip diff. Several overlap existing task sase-x5 examples, but I did not sweep them into this status-strip phase.

[2026-09-10T23:04:45Z · sase-z4.6.5.4.4] Settled the capacity-strip text by confirming the existing AgentInfoPanel render matches the contract (capacity units like 0.0/10.0 before the status bracket), then regenerated the stale agents-pane PNG corpus deliberately. Baseline at HEAD 74a4e4282: agents-pane visual subset reported 87 failed / 16 passed. Updated 90 PNG goldens only from artifacts whose expected-vs-actual diff boxes were confined to the status-strip row; independent HEAD-vs-working image audit reported changed_pngs=90, status_strip_only=90, non_status_strip=0, y-ranges (91,116), (92,115), (93,115). Inspected representative expected/actual crops (agents_list, reserved tribe wait, waiting family child, neighbor modal) and confirmed the change is old [N/10 running] strip text becoming the new N.N/10.0 [N running] form. Verified: just test-visual -- tests/ace/tui/visual/test_ace_png_snapshots_agents.py (10 passed); just test-visual -- tests/ace/tui/visual/test_ace_png_snapshots_agents_clans.py::test_clan_tree_fold_levels_png_snapshots (1 passed); final full agents-pane subset run reported 82 passed / 21 failed with fresh remaining artifacts all non-strip/body diffs, recorded separately as a PROPOSED FOLLOW-UP and not swept into this phase. just check was run and failed at the known unrelated feature-flag lint gate: live flag bead sase-z0 has no registry definition for key link_events; fmt, markdown fmt, keep-sorted, ruff, and mypy passed before that failure. sase bead epic-symbols sase-z4.6.5.4.4 reported no --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-z4.6.5.4.1](sase-z4.6.5.4.1.md) ✓ · ⧖ 2026-09-10
- **Depends on:** [sase-z4.6.5.4.3](sase-z4.6.5.4.3.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-z4.6.5.4.5](sase-z4.6.5.4.5.md) ◐ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.6.5.4.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z4.6.5.4.4/README.md) | [sase-z4.6.5.4.4](sase-z4.6.5.4.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3e39ebd`](https://github.com/sase-org/sase/commit/3e39ebdce2c297430b17da09760bf23ceb2cce4a) | test(tui): refresh capacity-strip PNG goldens | [sase-z4.6.5.4.4](sase-z4.6.5.4.4.md) | 2026-09-10 19:07:28 EDT |
