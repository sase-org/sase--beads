# Bead: sase-1jm.9 — Finish the Agents Archive epic before sase-1jm lands

[Bead Pages](../README.md) / [sase-1jm](README.md) / sase-1jm.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.land.md) · **Assignee:** `sase-1jm.9.land`
**Created:** 2026-10-12 14:50:50 EDT · **Closed:** 2026-10-13 07:12:54 EDT
**Plan:** [202610/agents\_archive\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_completion.md)

## Previously Closed

> ↺ Closed 2026-10-13T05:14:11Z · done
>
> (none)
>
> Reopened 2026-10-13T10:04:18Z by a status update

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/agents_archive_completion.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 8 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_completion.md

<!-- sase:links:end -->

## Description

Every promise of plan:202610/agents_archive_view.md holds on master with no flag residue. The retired Artifacts strip, the saved-query migration, the Archive chooser, restore, link arrivals, the shelf and bridge, and light-row Record behave as the plan says, with tests, goldens, and benches as proof, so the sase-1jm land agent can close the epic.

## Notes

[2026-10-13T04:16:13Z · sase-1jm.9.land] LAND TRIAGE (sase-1jm.9.land, master 1230bb32c1) of every PROPOSED FOLLOW-UP on phases .1-.8.
(1) EPIC WORK, planned in the lander tale: the clean-base failures that sase-1jm/sase-1jm.9 caused and that still fail at 1230bb32c1. These are .4 #1, .7 #2, .8 #2 and parts of .2 #1, .5 #1 and .6 #1.
  - test_quitting_from_archive_persists_grouping_only still asserts the eager grouping read that ba89d2a6db made lazy.
  - test_node_finder_modal.py::test_rapid_keystrokes_coalesce_to_final_query and ::test_dismissed_modal_releases_snapshot_rows_without_gc broke in ba89d2a6db, which made the Archive section unconditional. Each keystroke now rebuilds the list twice (a real perf bug), and the gc test's view baseline is stale.
  - test_path_label_exemptions_name_existing_sites_and_rationales keeps the stale revive_agent_modal.py exemption after ba89d2a6db deleted that file (.8 #1).
  - test_agent_jump_legend.py::test_dismissed_marker still expects "revive" after jump_opens_archive=yes (.3 #2, .4 #2, .7 #3). Its sibling test_neighbors_map_shows_dismissed_revive_cells was already fixed by 1230bb32c1.
(2) DECLINED, already owned:
  - test_tui_app_import_stays_under_startup_budget belongs to sase-1ic. tools/tui_import_closure --diff 101c853939 shows +0 modules from this epic.
  - test_project_shown_when_no_patch and test_workflow_snapshot_render_reads_state_once_and_uses_parsed_data belong to sase-1k4 (.2 #1, .5 #1, .8 #2).
  - The sase-core federation_worker flake belongs to sase-1gz (.7 #1).
  No +1, because each phase's triage already named the owner.
(3) DECLINED, no longer reproduce at 1230bb32c1:
  - The New Project test-waits lint from .1 #2: tools/check_test_wait_helpers exits 0.
  - test_source_groups_hidden_counts_and_hidden_filter and test_mark_save_preview_and_revive_saved_agent_group pass.
(4) CREATED flake task sase-1kf from .6 #1: test_ace_page_restores_fast_startup_overrides_after_success. In 3 scoped check runs since 2026-10-11, which predates this epic, an earlier test leaked the AcePage _collect_artifacts_project_choices override. Related links go to sase-j7 and sase-1a8.

[2026-10-13T04:18:36Z · sase-1jm.9.land] LAND VERIFICATION (sase-1jm.9.land, master 1230bb32c1): 4 helper audits checked phases .1-.8 against source and commits. Every plan item is implemented, except for gaps now planned in the lander tale: (a) 5 epic-caused failing tests: the stale revive_agent_modal path-label exemption; the Node Finder double rebuild per keystroke from ba89d2a6db plus the stale gc baseline; the parking test that predates the lazy grouping load; and test_dismissed_marker revive copy. (b) Collapsed or marked container restore restores nothing while the chooser claims N members, and with only a collapsed container marked it executes 0 restores. (c) The shelf paints 'updating…' instead of keeping the last snapshot, and ⏎ during a recount loses the carry. (d) The Node Finder opened cold never upgrades from 'Archive warming…'. (e) %j reads the selection off-thread. (f) Hand-built chooser goldens: the marked one says 'shows it again', and the Fork glyph renders as tofu; the restored-row golden hides the dimming. (g) Missing tests: y in the Archive view, ,a from Beads, no count per keystroke, and container/marks restore proof. (h) Cleanups: a beta docstring, the redundant artifact_tabs branch, a dead empty_state guard, a _when_enabled test name, and a stale Justfile comment. (i) Docs: ace.md Artifacts headings and revive-modal mentions, and artifacts_pane_contract.md. Accepted as is: target_for_ref_kind('agent') keeps the identity mapping, because agent refs are intercepted at both follow sites when the pane is retired. Integration: the 10 non-epic commits since the epic began (5cb48bdd36 through c69c31236f) need no change; there are no stale references to deleted symbols, and Projects-pane keys do not collide with y or ,a. epic-symbols for sase-1jm.9 and sase-1jm are empty.

[2026-10-13T05:14:11Z · sase-1jm.9.land] Landing verification: all 8 phases checked against source and commits; gaps closed by this tale (5 epic-caused tests fixed, collapsed/marked container restore via corpus resolver with resolved target list, shelf keeps last snapshot with answerable carry, Node Finder warms via provider retry, %j captures at keypress, y Archive copy, Beads ,a, chooser goldens from real model with font-safe fork glyph and visible dimming, cleanups and docs). Integration review: drift since 1230bb32c1 is New Project wizard only, no Archive impact. Follow-up triage already on bead (sase-1ic import budget, sase-1k4 project/snapshot, sase-1kf flake). Focused suites green, symvision clean, mypy clean, targeted goldens recaptured and inspected.

[2026-10-13T10:04:18Z · bryanbugyi34@gmail.com] I think this work is complete but the agent failed and left the parent epic open so I'm rerunning an epic lander agent.

[2026-10-13T11:12:35Z · sase-1jm.9.land] LAND TRIAGE, rerun (sase-1jm.9.land, master 3c08c4676f). Re-read every PROPOSED FOLLOW-UP on .1-.8; outcomes match note #1. EPIC WORK, now fixed in this landing: grouping-only parking test (.4 #1, .7 #2), Node Finder rapid-keystroke and gc tests (.2 #1, .5 #1, .6 #1), and test_dismissed_marker revive copy (.3 #2, .4 #2, .7 #3). test_neighbors_map_shows_dismissed_revive_cells was fixed by 1230bb32c1. The stale revive_agent_modal path-label exemption (.8 #1) was dropped on master by 0db1d4d387. DECLINED, already owned: the import budget belongs to sase-1ic. This run's +1 says 3517 modules against the 3513 cap, and tools/tui_import_closure --diff HEAD shows +0 from this landing. The Project: fake header test and the workflow-snapshot test belong to sase-1k4. The federation_worker flake belongs to sase-1gz (.7 #1). The fast-startup-overrides flake belongs to sase-1kf (.6 #1). DECLINED, no longer reproduces: the test-waits lint (.1 #2); the lint stage passed in check 340199e56682f532ca76bf69e2775b08. NEW FROM THIS CHECK, not caused by the epic: test_proc_producer_inventory is stale after the New Project apply split 35e9768444; CREATED ci task sase-1kg. test_sdd_git_identity_survives_empty_home_subprocess hit its 180 s timeout under load; +1'd duplicate sase-120. DECLINED: the docs agent's 8ad526f8d0 note that Archive Open chat opens $EDITOR without a read-only mode. The plan defines this read as never reviving, marking read, or writing, and the opener honors that. Forcing an editor mode is out of scope.

[2026-10-13T11:12:54Z · sase-1jm.9.land] Landing rerun (sase-1jm.9.land, master 3c08c4676f). The first landing tale's code never reached master: its muse provider crashed at finalization ('_GeneratorContextManager' has no attribute 'args'), and the workspace was reset. 4 epic-caused tests still failed on master. I recovered its 72 recorded edit_file calls from the muse session log, replayed them (all anchors matched; master's 0db1d4d387 already had the path-label fix), and reviewed every change against the plan. I rewrote the parts that fell short. CONTAINER/MARKS RESTORE: the tale's resolver sent the raw 'in:archive' query to the corpus and capped rows() at the group's root count, which truncated members, and its tests mocked the resolver. The plan is now captured on the event loop and resolved off-thread (summary plus rows() with the container expanded, limit = roots + member_count). One ArchiveRestoreTargets per chooser open drives both the label count and the executed keys, and its rows hydrate collapsed members. New test_agent_archive_restore_containers.py proves collapsed, expanded, container-only-marked, and container-plus-run restores through the real _do_revive_agents over a real column model and model corpus, plus chooser label == executed count. SHELF: dropped the dead 'loading' paint so the last snapshot stays until the recount lands. On ⏎ the shelf carries the committed filter only when the Archive can answer it: the landed snapshot decides, or during a recount the agents-archive profile parse with no I/O (the tale's check was always true). Added a mounted test proving typing in the filter bar never counts and commit counts once. Node Finder: single rebuild per keystroke (project=False); a cold Archive fills via a bounded provider retry (0.5 s x 30 plus each refilter). %j captures the run at keypress. Tests: y-copy, ,a from Beads, lazy grouping, and gc baseline. Goldens: chooser and marked built from the real model with ⎇ fork glyph; restored toast with cursor moved off the dimmed row. Inspected all three; targeted --check under TZ=UTC was clean over 25 Archive and Node Finder goldens. Cleanups and docs per the tale, plus corrected the ace.md container-restore and Node Finder warming text that the post-epic docs refresh had written for the old behavior. Verification: 247 focused tests green; mypy, symvision, and just fmt clean. sase tool run check 340199e56682f532ca76bf69e2775b08 ran the full lane: 55461 passed, 5 failed, none from this epic (sase-1ic, sase-1k4 x2, sase-120 +1, new sase-1kg). Integration: post-epic commits 826cad0513..3c08c4676f are New Project and docs only. No Archive source drift; the docs refresh was corrected as above. epic-symbols for sase-1jm.9 and sase-1jm are empty. Follow-up triage is in the preceding note.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.9.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.land/README.md) | [sase-1jm.9](sase-1jm.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`010185b`](https://github.com/sase-org/sase/commit/010185b0c47e1c9c70fd90e4b21149a4fb445753) | fix(agents-archive): land container restore, shelf, and Node Finder fixes for sase-1jm.9 | [sase-1jm.9](sase-1jm.9.md) | 2026-10-13 07:43:22 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.9.1--2][1] | Need epic decisions governing phase implementation | 1 |
| read-by | [agent:sase-1jm.9.2][2] | Need epic DECISIONS and parent scope | 1 |
| read-by | [agent:sase-1jm.9.4--2][3] | Need epic DECISIONS and notes for phase close | 2 |
| read-by | [agent:sase-1jm.9.5][4] | Need epic DECISIONS | 1 |
| read-by | [agent:sase-1jm.9.6--3][5] | Verify closing the assigned phase did not close its parent epic | 1 |
| read-by | [agent:sase-1jm.9.7][6] | Need parent epic DECISIONS for record-light-rows | 2 |
| read-by | [agent:sase-1jx.12.1.land][7] | Need the remaining archive epic scope before noting jump-legend failures | 1 |
| read-by | [agent:toobig-7v.new_project_apply.0][8] | Check the active Archive epic child for the stale revive-agent exemption follow-up. | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.9.1.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.9.4.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.5/README.md
[5]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.9.6.md
[6]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jm.9.7/README.md
[7]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.12.1.land/README.md
[8]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-7v.new_project_apply.0/README.md

<!-- sase:referenced-by:end -->
