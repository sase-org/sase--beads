# Bead: sase-1jm.9.4 — Lookup-first link arrivals and selection that survives clearing

[Bead Pages](../README.md) / [sase-1jm.9](sase-1jm.9.md) / sase-1jm.9.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.land.md) · **Assignee:** `sase-1jm.9.4` · **Size:** medium
**Created:** 2026-10-12 14:50:51 EDT · **Closed:** 2026-10-12 20:44:19 EDT
**Plan:** [202610/agents\_archive\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_completion.md)

## Description

arrivals-finish: look up before opening the Archive so a miss keeps context, reveal filter-hidden agents across agent tabs and folds, keep the Archive selection when name: is cleared, point target_for_ref_kind agent at the Agents tab, test ,a from another tab, and fix the link-follow docs.

## Notes

[2026-10-12T22:23:17Z · sase-1jm.9.4] PROPOSED FOLLOW-UP: tests/ace/tui/test_agent_archive_parking.py::test_quitting_from_archive_persists_grouping_only fails identically on the clean base tree (assert state.archive.grouping == "project" gets "day"; verified via stash at c4d84f9a1a), so it is environmental/pre-existing and unrelated to arrivals-finish; no task bead tracks it (bead search "archive grouping persists" empty); needs an owner to triage the grouping-preference read in init_agents_archive_view_state

[2026-10-12T22:23:27Z · sase-1jm.9.4] PROPOSED FOLLOW-UP: tests/ace/tui/widgets/test_agent_jump_legend.py::test_dismissed_marker and test_agent_jump_panel_prefix.py::test_neighbors_map_shows_dismissed_revive_cells fail identically on the clean base tree (verified via stash at c4d84f9a1a); both expect the word "revive" while the tree renders jump_opens_archive=yes copy ("gone archive"); already recorded as sase-1jm note #11 by observer sase-1jx.12.1 as staying on sase-1jm, so no new task created — land agent owns the copy/expectation call

[2026-10-12T22:29:03Z · sase-1jm.9.4] VERIFICATION (arrivals-finish): focused suites green on the final tree — test_archive_arrivals (5, lookup-first hit/miss/race), controller lookup, link-follow family incl. 4 new retired-routing/confirm-first/fold tests (135), jump/seam/facade/rail batch (102), parking incl. 2 new keep-selection tests, remaining_proof mounted incl. arrival-clear-name flow and ,a-from-Artifacts (10). sase tool run check lint stages all green (fmt, ruff, mypy, flags, symvision with sase-1jm.9.5(reveal_filtered_loaded_agent) row). Full just check verdict delegated to the prepared verify monitor. Base-identical failures (grouping persists, 2 jump-legend revive) recorded as PROPOSED FOLLOW-UP above; epic-symbols clean for this phase.

[2026-10-13T00:44:19Z · sase-1jm.9.4--2] arrivals-finish verified: focused suites green (test_archive_arrivals 5, controller lookup, link-follow family 135 incl. 4 new, jump/seam/facade/rail 102, parking +2 new keep-selection, remaining_proof 10 incl. arrival-clear-name and ,a-from-Artifacts); lint stages green. Full just check: 12 failed = 10 KNOWN + 1 FLAKY + 1 NEW where NEW test_quitting_from_archive_persists_grouping_only fails identically on clean base worktree at c4d84f9a1a (assert day==project), recorded as PROPOSED FOLLOW-UP; epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1jm.9.1](sase-1jm.9.1.md) ✓ · ⧖ 2026-10-12
- **Blocks:** [sase-1jm.9.5](sase-1jm.9.5.md) ◐ · ⧖ 2026-10-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.9.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.9.4.md) | [sase-1jm.9.4](sase-1jm.9.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a27c625`](https://github.com/sase-org/sase/commit/a27c6252f38fc1c16afea668e301ace616e91fba) | feat(archive): lookup-first link arrivals and selection that survives clearing | [sase-1jm.9.4](sase-1jm.9.4.md) | 2026-10-12 20:46:20 EDT |
