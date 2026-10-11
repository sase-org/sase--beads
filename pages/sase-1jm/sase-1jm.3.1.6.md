# Bead: sase-1jm.3.1.6 — Archive action isolation, caller audit, footer, and help

[Bead Pages](../README.md) / [sase-1jm.3.1](sase-1jm.3.1.md) / sase-1jm.3.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.md) · **Assignee:** `sase-1jm.3.1.6` · **Size:** medium
**Created:** 2026-10-10 20:21:22 EDT · **Closed:** 2026-10-11 14:45:28 EDT
**Plan:** [202610/agents\_archive\_view\_phase.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_phase.md)

## Description

action-boundary: audit every Agents selected-agent caller and route read operations through the typed view-aware selection while live actions use Inbox-only selection. Add explanatory guards for live-only keys and tab or tribe moves, independent Archive marks, a view-specific conditional footer, and the Archive help box. Preserve deck keys and the parent's later restore, route, bridge, and Record extension seams. Verify Archive rows do not enter Inbox accounting or bulk actions.

## Notes

[2026-10-11T18:37:16Z · sase-1jm.3.1.6] Action-boundary caller audit (86 _get_selected_agent sites): read-via-typed-selection = clipboard/_agents.py 5 copy readers + _palette._build_agent_context (resolve_agents_read_agent -> hydrated Archive agent, Inbox fallback), fork/copy parent seam archive_read_target (no chooser); live-mutation guarded with toast = x kill, X cleanup panel, s save-marked, S bulk-status, w reword/wait, W wait-for, A accept/HITL/auto-approve (+toggle_auto_approve), R retry, n rename, N tribe modal, U unread toggle, [/] tab cycle + tab picker; availability gate hides the same names from palette while Archive owns panel; view-nav j/k/g/G/h/l/J/K/Enter already Archive-routed via route_archive_key; Inbox-accounting (unread/attention/load/runner slots/clans/auto-dismiss/%wait/bulk/tab totals/Inbox marks) never consults Archive rows; live reply-follow stays Inbox-only by design. Guard coverage: every guarded entry returns before touching selection/marks/unread.

[2026-10-11T18:37:42Z · sase-1jm.3.1.6] Contracts for later phases: guards guard_archive_live_action(owner, action) + ARCHIVE_LIVE_ONLY_ACTIONS in actions/agents/_archive_actions.py (toasts name archived row, hint ,a, never mention restore); Archive marks on ArchiveViewState.marks by stable identity via toggle/clear_archive_mark(s) (m/u routed in marking.py, banners/tails/pulse unmarkable), archive_marked_count for footer, archive_marked_run_keys expands containers from light members for the parent bulk-restore builder (epic-symbol parked on sase-1jm.3); footer update_archive_bindings/_compute_archive_bindings shows read/mark/unmark/expand/cards/blocks/view only, parked Inbox selection never reaches it; help Archive (read-only) box documents ,a/j/k/g/G/l/h/J/K/Enter/m/u/o//filter (descs <=32 chars, 57-col box); public agents_archive_view_state(owner) seam added to _archive_view for consumers; no keymap/default_config changes (no rebinding); Enter-restore deliberately unadvertised (parent chooser owns it).

[2026-10-11T18:44:57Z · sase-1jm.3.1.6] PROPOSED FOLLOW-UP: check run 9c43d3572ffccbeefcc15c66b36b8aa6 shows 4 failures, none caused by this phase — test_app_import_budget (3516 vs 3513 cap, tools/tui_import_closure --diff merge-base proves +0 modules from this phase; same overage already recorded on sase-1jm.3.1.5) plus 3 load flakes green on immediate re-run (test_sdd_git_identity_survives_empty_home_subprocess, test_watchdog_stops_unjoined_run_when_starter_dies, test_inline_caller_group_sigkill_leaves_no_survivors; host load1 ~30 during the lane).

[2026-10-11T18:45:28Z · sase-1jm.3.1.6] Action-boundary done: live-only x/X/s/S/w/W/A/R/n/N/U/[/]/picker toast (,a hint, no restore promise) and no-op via guard_archive_live_action + palette availability gate; copy readers resolve hydrated Archive agent via resolve_agents_read_agent; independent Archive m/u marks on stable identities (banners/tails/pulse unmarkable, Inbox marks parked); conditional Archive footer (read/mark/unmark/expand/cards/blocks/view) and Archive (read-only) help box; parent fork/copy (archive_read_target) and bulk-restore (archive_marked_run_keys) seams parked as epic-symbols on sase-1jm.3. Verified: 25 new action-boundary tests + 54 neighboring archive/marking/help/clipboard tests green; just lint green incl symvision; sase tool run check 9c43d3572ffccbeefcc15c66b36b8aa6 all lint green, 54735 passed, 4 failed all pre-existing/flakes (+0 import modules proven, recorded as follow-up). No epic-symbol leftovers for this phase.

## Dependencies

- **Depends on:** [sase-1jm.3.1.5](sase-1jm.3.1.5.md) ✓ · ⧖ 2026-10-10
- **Blocks:** [sase-1jm.3.1.7](sase-1jm.3.1.7.md) ✓ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.3.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.6/README.md) | [sase-1jm.3.1.6](sase-1jm.3.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4841439`](https://github.com/sase-org/sase/commit/4841439aeed3e217ec0e3c7037786ddb5c8fd7eb) | feat(agents): isolate Archive action boundary with read-only guards | [sase-1jm.3.1.6](sase-1jm.3.1.6.md) | 2026-10-11 16:08:20 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.3.1.6][1] | Declaration recovery: need bead status to choose bead_action | 5 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.3.1.6/README.md

<!-- sase:referenced-by:end -->
