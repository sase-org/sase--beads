# Bead: sase-1rq.2.1.5.1.1 — Make the Files reserve regression deterministic

[Bead Pages](../README.md) / [sase-1rq.2.1.5.1](sase-1rq.2.1.5.1.md) / sase-1rq.2.1.5.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2.1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.5.md) · **Assignee:** `sase-1rq.2.1.5.1.1` · **Size:** medium
**Created:** 2026-11-07 11:09:41 EST · **Closed:** 2026-11-07 13:03:57 EST
**Plan:** [202611/full\_ci\_remaining\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202611/full_ci_remaining_repairs.md)

## Description

files-reserve: resolve sase-1qd by diagnosing the initial short-extent setup timeout in test_trailing_reserve_remeasures_when_flag_already_enabled; preserve the real remeasurement regression and verify under coverage/load without raising timeouts. Coordinate with contention phase sase-1rq.2.1.4.

## Notes

[2026-11-07T17:41:55Z · sase-1rq.2.1.5.1.1] OWNERSHIP SPLIT (sase-1qd node): this phase owns tests/ace/tui/widgets/decks/test_files_anchor_ownership.py::test_trailing_reserve_remeasures_when_flag_already_enabled and its production remeasure trigger (SectionViewMixin.refresh_section_layout_reserve in src/sase/ace/tui/widgets/prompt_panel/_section_view.py). Contention phase sase-1rq.2.1.4 owns runner survival and any other contention failures; if it meets this node, it reuses this fix (landing via host completion from this phase) instead of a separate repair or quarantine.

[2026-11-07T18:03:36Z · sase-1rq.2.1.5.1.1] ROOT CAUSE + FIX (sase-1qd): CI job 128401500987 timed out in the setup wait (line 364). Instrumented probe (old setup, just test-cov conditions: tools/run_pytest cov, SASE_PYTEST_WORKERS=3, taskset -c 0,1, decks dir + repeats) failed 14/270 reps; every failure had the paged->spread _restore already run (reserve on, max_scroll_y=6) AND spread._layout_required=True with that _layout_updates generation already measured by a screen reflow. Textual 8.0.1 refresh(layout=True) only bumps _layout_updates when no layout is pending, and _get_box_model caches by it, so clear_cached_dimensions()+refresh(layout=True) never re-called get_content_height (0 measures over 5s). Not delayed rendering/content change. Fix: SectionViewMixin.refresh_section_layout_reserve also clears _box_model_cache (production remeasure trigger, shared with Main block nav). Test: setup now waits for the restore-landed reserved state (_ready_reserved_spread) and drives the production refresh_section_layout_reserve(); setup waits name anchor/real height/extent/reserve/section+anchor generation/layout_pending/layout_updates on timeout; new deterministic test_reserve_remeasure_survives_pending_measured_layout runs the interleave synchronously. No timeout raised, no assertion weakened.

[2026-11-07T18:03:41Z · sase-1rq.2.1.5.1.1] VERIFICATION: (1) loaded: taskset -c 0,1 env REPEAT_N=150 SASE_PYTEST_WORKERS=3 .venv/bin/python tools/run_pytest cov tests/ace/tui/widgets/decks/ + scratch repeat wrapper (150x trailing node, 50x new test) -> 933 passed, 0 failed (same conditions failed 7/120 and 7/150 before). (2) Mutations: removing the 2e68053dab panel/enable remeasure triggers -> trailing test fails 8/8 with the original CI signature (max_scroll_y=0 live_target=6 pending=1 retry=8); removing only the _box_model_cache clear -> new test fails 12/12; both restored. (3) tools/run_pytest fast on decks dir + prompt_panel section-navigation/bottom-pin + main_deck_reply_steal_recovery + live_reply_follow_mounted* -> 767 passed. (4) just test-visual -- agents_deck_views_files/deck_blocks/deck_views_main -> check clean, 18 unchanged. (5) sase tool run check 1f6a2e195aedc1bf5a23fa4fe0a9397e succeeded. Landed via host completion from this phase (find the sase-1rq.2.1.5.1.1 commit on master; SHA not known at turn end). Integration re-check: tools/run_pytest fast tests/ace/tui/widgets/decks/test_files_anchor_ownership.py

[2026-11-07T18:03:47Z · sase-1rq.2.1.5.1.1] PROPOSED FOLLOW-UP: Textual 8 swallows layout remeasures behind a measured pending request — any Static.update()/refresh(layout=True) on a widget whose pending layout generation a reflow already measured keeps the stale box-model height; only the section reserve path is hardened here. Consider an upstream Textual report or a shared remeasure helper for other auto-height views.

[2026-11-07T18:03:57Z · sase-1rq.2.1.5.1.1] Root-caused sase-1qd: Textual 8 refresh(layout=True) does not advance the box-model cache key while a layout is pending, so the reserve remeasure was swallowed after a reflow measured the spread first (14/270 loaded probe failures, all with layout_pending=True and no remeasure). Fixed refresh_section_layout_reserve to clear _box_model_cache; regression setup now waits for the restore-landed state and uses the production trigger with diagnostics; new deterministic interleave test. Loaded cov 3-worker/2-CPU run 933/933 passed; trigger-removal mutation fails 8/8, fix-removal fails 12/12; nearby deck/section/Main tests 767 passed; targeted visual check clean; sase tool run check 1f6a2e195aedc1bf5a23fa4fe0a9397e succeeded. No timeout raised.

## Dependencies

- **Blocks:** [sase-1rq.2.1.5.1.4](sase-1rq.2.1.5.1.4.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.5.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.5.1.1/README.md) | [sase-1rq.2.1.5.1.1](sase-1rq.2.1.5.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`da15614`](https://github.com/sase-org/sase/commit/da1561407ab03db299959ec3ab8e2a5fadafb1e3) | fix(tui): keep Files spread reserve remeasure from being swallowed | [sase-1rq.2.1.5.1.1](sase-1rq.2.1.5.1.1.md) | 2026-11-07 13:05:20 EST |
