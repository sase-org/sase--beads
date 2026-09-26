# Bead: sase-17d.12 — Finish landing agent data decks - Files spread, live spread checks and the j/k bench

[Bead Pages](../README.md) / [sase-17d](README.md) / sase-17d.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17d.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17d.land.md) · **Assignee:** `sase-17d.12.land`
**Created:** 2026-09-25 08:46:12 EDT · **Closed:** 2026-09-25 19:49:18 EDT
**Plan:** [202609/finish\_agent\_decks\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_agent_decks_landing.md)

## Description

The Files deck really spreads in the live app, the deck visual tests that are broken at master pass again, live spread screenshots of Main, a spread/paged split and Files have been inspected and any separator or title-pill defects fixed, and before/after j/k bench numbers for the SINGLE and LEFT_RIGHT layouts are recorded with every budget miss explained, so the land agent of epic sase-17d can close it.

## Notes

[2026-09-25T23:49:18Z · sase-17d.12.land] Verified sase-17d.12 at ed548d3e26. All three phases are closed and their notes match the tree.

Files spread (sase-17d.12.1, 27d03a7b72): DeckPanelFilesMixin.on_worker_state_changed gates on WorkerState. SUCCESS applies event.worker.result when it is a FilesSpreadProbe; ERROR and CANCELLED clear _files_pending_probe and leave the mode unchanged; other workers and non-terminal states are ignored. The probe worker uses exit_on_error=False. _apply_files_spread_probe is gone. The session fold-levels PNG test scrolls to agent-prompt. sase-18m and sase-18y are closed. 19 focused tests passed, including the live Files spread pilot, both Ctrl+J separator-anchor tests, and the zoomed-tribe pilot.

Separators (sase-17d.12.2, 59bf17d53f): Main scroll_to_card and Files Ctrl+J use spread_anchor_row / _files_anchor_row. spread_body_start and _files_body_start stay anchor+1 and are used only for spread/paged transition restore. Inspected agents_decks_single_main_reply_120x40 (Reply separator and Reply pill at the top, spread tag), agents_decks_single_files_spread_160x40 (no separator before the first page, page-label separator on the second, filename also in the page heading, spread tag), and agents_decks_left_right_ratio_70_focus_left_120x40 (spread Main beside a narrow paged Tools column whose subtitle truncates). Live `sase screenshot` of the real archive was blocked by a plan-gate overlay in the phase; the visual goldens are the inspection record.

Bench (sase-17d.12.3): BENCH RESULTS note stands. Baseline a054efc585 vs final 04cf2b1765, SINGLE and LEFT_RIGHT, interleaved, loadavg 19-25. Row j/k p95 about 19-24 ms and panel J/K p95 55-109 ms overlap across trees; 250-365 ms stalls land on both trees. Classified host noise, no deck regression. Two later commits (6beedbc118 queue-capacity plumbing, ed548d3e26 bead close records) do not touch deck rendering.

Integration: commits since 27d03a7b72 that touch decks are the deck picker (ce1336eec7, 31a37bd7b9) and later header/context goldens. show_deck_in_other_panel calls show_deck, so Files spread and separator scroll stay on the shared path. Node jump only reveals rows. OwnerRecordLookup is already a public Protocol imported by cli_work_cleanup_selection. No duplicate probe or scroll path to retarget. epic-symbols for this epic: none.

Follow-ups from sase-17d.12.2:
- +1 sase-18n (notes #1, #2, #8: narrow top-bar usage wait_for_startup timeouts).
- +1 sase-13a (note #3: test_alias_sbd_completes_static_bead_tree).
- +1 sase-120 (note #4: test_sdd_git_identity_survives_empty_home_subprocess).
- New flake tasks, marked ready: sase-19t (test_handoff_end_to_end_settles_through_proc), sase-19u (test_executor_records_samples_and_show_lists_them), sase-19v (test_legacy_no_commit_state_maps_to_approve_choice WaitForScreenTimeout), sase-19w (test_startup_update_toast_png_snapshot notifications timeout; related to sase-144, different failure).
- Declined a second +1 on sase-18t: note #10's handoff notification store-lock was already corroborated by sase-17d.12.2--3.
- Declined, no longer failing at ed548d3e26: queue completion (note #5 / #10; test_queue_capacity_completion_describes_limit now expects the <M>x text and passed), xprompt parity's extra 1.5x insertion (the expected list includes 1.5x), var schema 32 vs 31 (note #6; the upgrade test passed at schema 33), tailnet pin (note #10; test_classify_tailnet_discovery_never_infers_pin passed), cleanup planner family wording (note #10; both planner tests now expect "parallel session still active" and passed), OwnerRecordLookup symvision (note #9; the Protocol is public).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.12.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17d.12.land/README.md) | [sase-17d.12](sase-17d.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@acdfd70`](https://github.com/sase-org/sase--plans/commit/acdfd702ede9db7f2fb21ced9be923e4760f53db) | docs(plans): mark agent deck epic plans done | [sase-17d.12](sase-17d.12.md) | 2026-09-25 20:01:10 EDT |
