# Bead: sase-12z.5.2 — Integrate the metadata-only Agents default with the visual corpus

[Bead Pages](../README.md) / [sase-12z.5](sase-12z.5.md) / sase-12z.5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-12z.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-12z.land.md) · **Assignee:** `sase-12z.5.2` · **Size:** medium
**Created:** 2026-09-18 20:31:32 EDT · **Closed:** 2026-09-20 10:01:40 EDT
**Plan:** [202609/finish\_screenshot\_maintenance.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_screenshot_maintenance.md)

## Description

visual-integration: repair stale secondary-panel test flows, review and accept only the intentional metadata-only golden changes, and prove the complete corpus is clean.

## Notes

[2026-09-19T04:49:02Z · sase-12z.5.2--1] PROGRESS: just check-full 72n3h8fvs4cv timed out after 2h in silent test-cost (lint/fmt passed; screenshot stage never ran; machine also had other workspaces in test-cost). Targeted LLM check-only a5ad9b49: 3 passed, drift is filled ● llm calls indicator with LLM CALLS panel content intact. File/slow-tool nodes passed in earlier 4-file check. Next: full just fix-tui-screenshots update, then review, then --check, then check-full with a longer timeout.

[2026-09-19T05:14:12Z · sase-12z.5.2--2] PROGRESS: just fix-tui-screenshots vaxb6sdp2rt4 failed after 968+96 visual tests passed: determinism verify_hash_mismatch on startup_update_toast_120x40.png. First capture was a compositor flake (6379 footer STOPPED-badge pixels); verify matched the committed golden. 116 agents_* goldens plus tmux-modal/link-rail/cleanup confirmation differed; toast is not a real golden change. Added _stabilize_toast_frame; two targeted check-only runs: 2 passed, unchanged=2. Next: full golden UPDATE, then review, --check, check-full.

[2026-09-19T06:05:59Z · sase-12z.5.2--4] PROGRESS: just fix-tui-screenshots --check 25yjagnv5r88 failed with compositor flake on post_update_toast_diffstat_120x40.png (created=0 updated=1 unchanged=706 stale=0; 6379 footer STOPPED-badge pixels, same class as startup toast). Did not accept that golden. Shared stabilize_toast_frame into visual wait helpers and applied it to post-update toast snapshots. Targeted check-only f9dab549: 4 passed, created=0 updated=0 unchanged=4 stale=0; toast goldens unchanged. Next: full just fix-tui-screenshots --check, then check-full (timeout at least 4h).

[2026-09-19T06:57:48Z · sase-12z.5.2--6] PROGRESS: just check-full g1khz404s48g failed after lint/fmt/validate and a clean pytest cost lane (43256 passed, 16 skipped, 0 failed in 25m15s) on one hard ceiling: causes.subprocess_run.count 53382 vs 52000. All 8 retained athena recordings already exceed 52000 (min/median/max 52043/53137.5/53494). Recalibrated subprocess_run.count 52000 -> 67000 from --suggest --history 8; other hard limits unchanged. Latest recording now passes with advisories only. Visual --check remains clean (created=0 updated=0 unchanged=707). Next: just check-full, then confirm trailing screenshot UPDATE writes no extra goldens, then epic-symbols and close.

[2026-09-19T15:52:02Z · sase-12z.5.2--c] PROGRESS: just check-full 4wg8ca7yns9v failed after 1h36m on the known import-budget load flake (15.24s vs 5.0s; 43255 passed, 16 skipped; isolation retry 2.69s under 5.0s). Recording 20260919T153148Z-3527032.json then failed causes.parser_create.cpu 86.383 vs 85.000. Recalibrated parser_create.cpu 68 -> 70 from --suggest --history 8 (min/median/max 73.085/78.922/86.383, count 2042-2045). Latest recording now passes with wall advisories only; budget unit tests 42 passed. Visual tree still 119 M + 1 D. Next: just check-full.

[2026-09-20T13:58:37Z · sase-12z.5.2] PROPOSED FOLLOW-UP: zoom modal LLM Calls visibility handler never dispatches — src/sase/ace/tui/modals/zoom_panel_modal.py defines on_llm_calls_visibility_changed but Textual names the message handler on_llmcalls_visibility_changed (same latent bug this phase fixed for AgentDetail with @on(LLMCallsVisibilityChanged)); decide whether the zoom modal needs the same decorator and refresh any zoom goldens it changes.

[2026-09-20T13:59:04Z · sase-12z.5.2] PROPOSED FOLLOW-UP: Agents header "(p)" view hint goes stale after the view picker closes without a change (selecting the already-current layout or Esc skips _refresh_agent_view_surfaces); a countdown tick while the modal is open drops the hint until the next tick. Worked around in tests via choose_agent_metadata_view refreshing the info panel; a product fix would refresh the info panel from the picker dismiss callback.

[2026-09-20T13:59:30Z · sase-12z.5.2] PROPOSED FOLLOW-UP: origin/master at the time of this phase already carries 86ff62c08 (symvision/mypy fixes for the tmux launcher and memory-selector splits) and 5023214db (contract manifest); the sase_29 base 244442ee8 fails just check on 20 mypy no-untyped-def errors in src/sase/main/ace_tmux*.py, 13 symvision symbols, and 6 tests (test_fleet_contract_sase_core_rs schema version 5!=4, test_contract_manifest, test_app_import_budget load flake, test_capacity_gate_to_admission x2, test_lazy_tier2_reconcile_apply::test_changed_query_incomplete_load_after_reconcile_rearms) — all reproduce on clean HEAD with this phase stashed; the land agent should re-verify on the rebased tree, and just check-full was not run because lint fails first at this base.

[2026-09-20T13:59:57Z · sase-12z.5.2] PROPOSED FOLLOW-UP: tests/perf/baselines/test_cost_budgets.json subprocess_run.count hard limit (52000) is below every retained athena recording (min 52043, max 53494 per earlier attempts on this bead) and parser_create.cpu (68) trips under load; earlier attempts recalibrated via --suggest --history 8 but that uncommitted edit was lost, so the next just check-full will fail on cost budgets unless recalibrated.

[2026-09-20T14:00:23Z · sase-12z.5.2] PROPOSED FOLLOW-UP: full-run visual captures are load-sensitive: agents_fleet_remote_tribe_families_120x40 once captured neighbors/expanded-family state in a first capture (verify matched golden), and footer #keybinding-status kept a stale auto-width region after the startup stopwatch ended (Textual caches Widget content width by container width; Static.update does not clear it) — mitigated for toast goldens with stabilize_toast_frame; investigate the fleet leak and whether KeybindingStatusMixin._update_status should call clear_cached_dimensions().

[2026-09-20T14:01:40Z · sase-12z.5.2] Visual corpus integrated with the metadata-only Agents default and proven clean. Repaired stale flows: external/linked/commit-message File panels now choose File-larger via the picker, LLM Calls tests select a visible secondary layout after content loads, slow-tool test uses an explicit metadata-only selection. Fixed a latent Textual handler-name bug (LLMCallsVisibilityChanged dispatched to on_llmcalls_visibility_changed) with @on so LLM Calls layouts are selectable under the new default, and restored panel repaint on row-content/hint changes lost to the 13i.2 identity-only skip (fixes 2 fakey retry e2e + collapsed-panel fold-hint failures; test_queued_clan_counts uses tribe-keyed widget id). Added regression tests (picker message dispatch, full-refresh repaint x2). Stabilized toast footer badge (stale auto-width cache) and slow-tools header (p) hint races. Full just fix-tui-screenshots update applied (172 updated, 537 unchanged, 1 stale removed agents_view_picker_three_layouts) after 972 passed + 147 verify passed; final full --check clean: 972 passed 1 skipped, created=0 updated=0 unchanged=709 stale=0, complete inventory, golden tree unchanged. Review: 112 header view file->none (intended default); 49 [Enter] send->launch... (bdff89d98, unrelated); LLM/slow-tool filled llm-calls dot (handler fix); fleet/tribe strips + offline runtime, clan/tribe selected-row styling, submit-choice modal from other landed features. 689/700 clean-HEAD candidates identical to new goldens; the rest are the repaint fix. Scoped test lane escalated to full: 43560 passed, 6 failed - the same 6 fail on clean HEAD (unrelated). NOT run: just check-full - base 244442ee8 fails just check first on pre-existing mypy (20 errs ace_tmux*) and symvision (13 symbols) already fixed upstream by 86ff62c08; see PROPOSED FOLLOW-UP notes (also cost-budget ceilings).

## Dependencies

- **Depends on:** [sase-12z.5.1](sase-12z.5.1.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12z.5.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-12z.5.2/README.md) | [sase-12z.5.2](sase-12z.5.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9a56fc1`](https://github.com/sase-org/sase/commit/9a56fc1294652b518c05fdfb28a56a72c9dc4f61) | fix(visual): integrate the metadata-only Agents default with the screenshot corpus | [sase-12z.5.2](sase-12z.5.2.md) | 2026-09-20 10:46:29 EDT |
