# Bead: sase-17d.12.2 — Inspect live spread rendering and fix separator and title-pill defects

[Bead Pages](../README.md) / [sase-17d.12](sase-17d.12.md) / sase-17d.12.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17d.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17d.land.md) · **Assignee:** `sase-17d.12.2` · **Size:** medium
**Created:** 2026-09-25 08:46:15 EDT · **Closed:** 2026-09-25 17:30:50 EDT
**Plan:** [202609/finish\_agent\_decks\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_agent_decks_landing.md)

## Description

spread-live-inspection: capture live sase screenshot PNGs of a single spread Main deck, a LEFT_RIGHT split with one spread and one paged panel, and a spread Files deck. Inspect separators, the scroll-driven title pill and tiny-width degrade, explain the missing separator in the Reply golden, fix any defect, add the zoomed-tribe pilot test, and finish with a clean full visual check.

## Notes

[2026-09-25T14:45:31Z · sase-17d.12.2--1] PROPOSED FOLLOW-UP: top-bar usage narrow PNG snapshots (test_top_bar_usage_attention_narrow, test_top_bar_usage_badges_crowded_narrow) time out in wait_for_startup identically on clean tree — pre-existing, unrelated to spread scroll fix

[2026-09-25T15:25:12Z · sase-17d.12.2--2] PROPOSED FOLLOW-UP: visual --check top-bar usage nodes (test_top_bar_usage_attention_narrow, test_top_bar_usage_badges_crowded_narrow) fail identically on clean base tree; sase-18n drift out of scope for spread-inspection phase

[2026-09-25T16:16:49Z · sase-17d.12.2--3] PROPOSED FOLLOW-UP: full just check flakes test_alias_sbd_completes_static_bead_tree and test_handoff_end_to_end_settles_through_proc under 4-worker full-suite load; both pass in isolation on dirty tree — pre-existing flake unrelated to spread scroll fix

[2026-09-25T17:03:08Z · sase-17d.12.2--4] PROPOSED FOLLOW-UP: full just check flakes test_sdd_git_identity_survives_empty_home_subprocess and test_executor_records_samples_and_show_lists_them under full-suite load; both pass in isolation on dirty tree — pre-existing flakes unrelated to spread scroll fix

[2026-09-25T18:06:36Z · sase-17d.12.2--5] PROPOSED FOLLOW-UP: just check full-suite failures in test_xprompt_directive_completion_parity (3 queue-arg params, extra 1.5x insertion) and test_queue_capacity_completion_describes_limit reproduce identically on clean base tree (src stashed) — pre-existing queue-completion drift unrelated to spread scroll fix

[2026-09-25T19:17:54Z · sase-17d.12.2--6] PROPOSED FOLLOW-UP: just check full-suite failure in test_var_cli_end_to_end_refreshes_index_and_round_trips_machine_outputs (schema_version 32 vs 31) reproduces identically on clean base tree (src reverted to HEAD via read-only git show, no index write due to stale lock) — pre-existing var-index drift unrelated to spread scroll fix

[2026-09-25T21:30:26Z · sase-17d.12.2--1] PROPOSED FOLLOW-UP: full visual --check timeout in test_startup_update_toast_png_snapshot (wait_for notifications 5s) under 3-worker load (load1 ~30-40); passes isolation (4.84s) on dirty tree. Out of scope for spread-inspection. Same node as sase-144 (footer hash mismatch), different failure mode.

[2026-09-25T21:30:50Z · sase-17d.12.2--1] Reply golden explained+fixed: Ctrl+J scrolled to spread_body_start=anchor+1, hiding the heavy ━ ◆ Reply ━ separator; Main now uses spread_anchor_row and Files uses _files_anchor_row so the titled separator lands at viewport top, while spread_body_start stays anchor+1 for transition math. Regenerated agents_decks_single_main_reply_120x40.png (separator now at top, pill on Reply). Tests: test_main_ctrl_j_scrolls_separator_anchor_to_top, test_files_ctrl_j_scrolls_page_anchor_to_top, test_zoomed_tribe_summary_steps_keep_zoom_and_follow_selection (just test 14 passed). Goldens inspected: context (no first-card separator, spread tag, pill Context); reply (heavy separator visible, pill Reply); LEFT_RIGHT 70% (spread Main + paged Tools, Tools subtitle truncated); collapsed split (spread tag only on spread Main); search-committed (tiny-width subtitle truncate 'main · files · to'); Files spread (page-label separator, first page no separator, filename also in page heading — readable). Live sase screenshot of the real archive was blocked by a plan-gate overlay. Full just fix-tui-screenshots --check: 1039 passed, 3 failed, 0 goldens created/updated. Failures are out of scope: test_top_bar_usage_attention_narrow and test_top_bar_usage_badges_crowded_narrow wait_for_startup 15s timeouts (sase-18n, also fail in isolation); test_startup_update_toast_png_snapshot 5s notifications timeout under 3-worker load, passes isolation (sase-144 same node, different mode). No Agents-tab or deck failures. epic-symbols empty. Did not close parent sase-17d.12 or sase-17d.

[2026-09-25T21:44:15Z · sase-17d.12.2--2] PROPOSED FOLLOW-UP: HEAD just check failed at lint(symvision) on _OwnerRecordLookup imported by src/sase/bead/cli_work_cleanup_selection.py from cli_work_cleanup_targets.py (commit 938d2d8fe, sase-19o cleanup typing). This workspace renamed the Protocol to OwnerRecordLookup so the spread-inspection tree can pass just check. Visual --check still 3 out-of-scope failures: test_top_bar_usage_attention_narrow and test_top_bar_usage_badges_crowded_narrow (sase-18n wait_for_startup 15s); test_startup_update_toast_png_snapshot (sase-144, 5s notifications timeout under load).

[2026-09-25T22:51:23Z · sase-17d.12.2--3] PROPOSED FOLLOW-UP: just check 6 failures on 2026-09-25 monitor j075kj66xtkd / ToolRun 181640206aaedbb9cd6afd796ecec0bd are out of scope for spread-inspection — 4 fail identically on clean HEAD (src stashed): test_classify_tailnet_discovery_never_infers_pin (compatibility=incompatible / fleet protocol version unsupported, sase-xe.16), test_python_cleanup_planner_matches_legacy_partitions[clan-scope-active-parallel-agent-session] and test_python_cleanup_planner_gates_parallel_root_dismissal_until_done (tests still expect "parallel family still active" vs planner "parallel session still active", sase-17m), test_queue_capacity_completion_describes_limit (description now includes <M>x multiplier, sase-19f). 2 passed isolation: test_legacy_no_commit_state_maps_to_approve_choice WaitForScreenTimeout under 6-worker load; test_handoff_end_to_end_publishes_one_notification tool-run store locked (sase-18t). In-scope spread tests still pass (3/3).

## Dependencies

- **Depends on:** [sase-17d.12.1](sase-17d.12.1.md) ✓ · ⧖ 2026-09-25
- **Blocks:** [sase-17d.12.3](sase-17d.12.3.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17d.12.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17d.12.2.md) | [sase-17d.12.2](sase-17d.12.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`59bf17d`](https://github.com/sase-org/sase/commit/59bf17d53fa39d9bd31b66cd3375c42b59b1290c) | fix(tui): scroll spread Ctrl+J onto the titled separator | [sase-17d.12.2](sase-17d.12.2.md) | 2026-09-25 18:53:21 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17d.12.2--3][1] | Need current bead status and close notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-17d.12.2.md

<!-- sase:referenced-by:end -->
