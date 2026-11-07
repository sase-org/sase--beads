# Bead: sase-1rq.2.1.5.1.3 — Stabilize the stranded modal and empty Beads captures

[Bead Pages](../README.md) / [sase-1rq.2.1.5.1](sase-1rq.2.1.5.1.md) / sase-1rq.2.1.5.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2.1.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.1.5.md) · **Assignee:** `sase-1rq.2.1.5.1.3` · **Size:** medium
**Created:** 2026-11-07 11:09:42 EST · **Closed:** 2026-11-07 14:42:14 EST
**Plan:** [202611/full\_ci\_remaining\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202611/full_ci_remaining_repairs.md)

## Description

visual-fixtures: identify and fix the state leaking into agents_stranded_resolve_modal_120x40 and artifacts_beads_empty_120x40; compare CI actuals with local captures, control the specific focus/layout or inbox seam, and prove exact matching with the normal and UTC environments.

## Notes

[2026-11-07T19:41:51Z · sase-1rq.2.1.5.1.3] PROPOSED FOLLOW-UP: Isolate process-global Agents row-overlay caches across all visual tests — agent_stranded._STRANDED_REPORT_CACHE, agent_wait_beads._WAIT_BEAD_STATUS_CACHE and agent_bead._BEAD_DISPLAY_CACHE survive between AcePage tests in one xdist worker (CI worksteal runs ~470 consecutive visual tests per process), so a capture can inherit stranded flags, wait counts and panel widths from an earlier test with the same bead ids. This phase isolates them only in test_ace_png_snapshots_agents_stranded.py; promoting an autouse fixture to tests/ace/tui/visual/conftest.py needs a full `sase tool run test-visual` comparison.

[2026-11-07T19:41:58Z · sase-1rq.2.1.5.1.3] PROPOSED FOLLOW-UP: Corroborating evidence for sase-1qb (no new task) — this phase full visual check reproduced capacity_inspector_120x40 failing first pass (expect_modal CapacityInspectorModal timeout) with Python 3.14 _DeadlockError importing sase.core.wait_dependency_resolution._artifact_state, then passing on recapture.

[2026-11-07T19:42:14Z · sase-1rq.2.1.5.1.3] visual-fixtures fixed on base c732c6e38e (tree lands via host completion; text patch also applies cleanly onto origin/master 578a317bcf). (1) agents_stranded_resolve_modal_120x40 — cause: test-order leak. CI worksteal runs the stranded module in one process; rows_and_clan left a stranded report and warm wait-bead status in process-global caches, so the modal first paint already showed [W2?1 D1] ⚐1 ▲▲. Reproduced byte-for-byte: CI actual md5 bae502d8 (identical in 4 CI runs) == local `just test-visual <module> -n 1` actual. Also a real UI defect: a stranded flag that widens a clan row never painted — _try_patch_agent_row declined (width_growth), the fallback rebuild skipped the panel because rows and paint key were unchanged, and the failed patch left its unpainted render cached. Fix: patch_row declines by invalidating the agent render-cache entry and clearing _panel_paint_key; _try_patch_agent_row clears the paint key on decline; the stranded module isolates the three caches per test; the modal test settles the startup warmup, publishes via _apply_bead_warmup_results and waits for ⚐1. Only that golden updated (inspected): it differs from the CI actual solely in the second wave pip (○ vs leaked ▲, 34x11 px). (2) artifacts_beads_empty_120x40 — cause: "inbox: " painted #1c1b1a (= background) because NotificationIndicator cached a transparent-foreground VisualStyle before the App had its color rule. On a fast-stylesheet cache hit AcePage dropped Textual queued initial refresh_css, so the App stayed unstyled until after Compose/Resize and under load the screen painted first; Textual never invalidates descendant visual styles. Same signature in CI run 42297547091 (artifacts_split narrow, commits_origin_legend). Fix: on a hit, swap that refresh for a parse-free stylesheet.update(app). Golden unchanged. Contention repro (2 CPUs, beads+split x40-80, -n12-16): before 2-4 failures per batch and 38-114 transparent-style events; after 2x160 runs, 0 failures and 0 events. Regressions: test_width_growth_decline_leaves_the_stale_row_to_a_rebuild and test_ace_page_fast_stylesheet_cache_styles_app_before_widgets_mount each fail with their fix reverted; the modal test times out on ⚐1 without the UI fix. Verified: `just test-visual` both selectors together clean (local and TZ=UTC, unstable=[]), each alone clean; stranded module -n 1 / default / UTC drifts only detail_header and blocked_detail (AGENT PROMPT heading family, red in CI too, owned by sase-1r2.6). Full `sase tool run test-visual` 9c022624: 110 drifts, all within CI run 42370668331 failure set, both selectors pass. 230 targeted nonvisual tests pass; `sase tool run check` 68aa87b6 succeeded.

## Dependencies

- **Blocks:** [sase-1rq.2.1.5.1.4](sase-1rq.2.1.5.1.4.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.5.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.5.1.3/README.md) | [sase-1rq.2.1.5.1.3](sase-1rq.2.1.5.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`960646e`](https://github.com/sase-org/sase/commit/960646e8cea50f80a19a08199be044fbfe55bf03) | fix(tui): stabilize the stranded modal and empty Beads PNG captures | [sase-1rq.2.1.5.1.3](sase-1rq.2.1.5.1.3.md) | 2026-11-07 14:43:39 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1rq.2.1.5.1.3][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.5.1.3/README.md

<!-- sase:referenced-by:end -->
