# Bead: sase-1ou.6.1 — Remove the stall in Files spread navigation and make CI timeouts diagnosable

[Bead Pages](../README.md) / [sase-1ou.6](sase-1ou.6.md) / sase-1ou.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ou.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.land.md) · **Assignee:** `sase-1ou.6.1` · **Size:** medium
**Created:** 2026-10-28 17:04:15 EDT · **Closed:** 2026-10-29 16:17:49 EDT
**Plan:** [202610/files\_spread\_ci\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202610/files_spread_ci_landing.md)

## Previously Closed

> ↺ Closed 2026-10-28T23:09:38Z · done
>
> (none)
>
> Reopened 2026-10-29T15:03:46Z by `sase bead open`

## Description

files-landing: rebuild the CI-like Python 3.12 / Textual 8.2.8 environment, prove with a deterministic real-widget test that pending Files navigation stalls once its bounded refresh-retry chain runs out after the last layout publish, make navigation resume on scroll-extent change instead, add state to the anchor-wait timeout message, and prove it with isolated and loaded loops in both Textual versions.

## Notes

[2026-10-28T23:09:38Z · sase-1ou.6.1] Stall fixed + timeouts diagnosable. Fix: DeckPanel watches Files VerticalScroll virtual_size; _on_files_scroll_extent re-arms pending nav via _reschedule_files_scroll_after_layout (bounded chain keeps 8-hop backstop, re-arms per extent change). wait_for_anchor_scroll gains diagnose param; Files call sites pass describe_files_nav (scroll_y/max/pending/retry/generation/confirmed + textual version); timeout and success condition unchanged. No assertions/timeouts/baselines changed; no baseline entries; sase-1a7 left open. Evidence: new test_stalled_navigation_resumes_on_scroll_extent_growth FAILS before (anchor_wait scroll_y=0 target=6 max=54 pending=1 retry=8) PASSES after. Isolated 50x each, both venvs (3.14/8.0.1 and scratch 3.12/8.2.8 outside repo per plan): regression 50/50+50/50, ctrl_j 50/50+50/50, superseding 50/50+50/50. Loaded decks-dir -n6 +48 spinners: 4/5 clean per venv; each single flake shows max_scroll_y=0 at timeout (extent never grew in-window under contention) and the same signature reproduces on the clean base tree (ctrl_j + late_layout fail there too), so it is the known pre-existing wait-vs-layout race, not a regression; scheduled Full CI proof stays with the land agent. sase tool run check: ruff/mypy/test-waits/changelog/terminology/docs/scoped-tests green; only 9 KNOWN pre-existing symvision in untouched files (verdict no_new_failures). Hypothesis confirmed, no course change. Untried plan routes (random order, pinned-CPU tui run, full non-visual pinned set) available to land agent if wanted.

[2026-10-29T15:05:03Z · sase-1ou.6.land--1] CI RECURRENCE (2026-10-29): scheduled Full CI 40879308061 at b10abafcf07450a22334253569725ea2a2251396 contains fix aaa88b002679ac9b12a5cdc4244426daa469011a (git merge-base --is-ancestor exit 0), but Python 3.12 job 123474405005 fails tests/ace/tui/widgets/decks/test_files_anchor_ownership.py::test_visible_paged_restore_still_moves_viewport at its first post-cycle_card(1) wait, line 130. Exact diagnostic: anchor_wait: scroll_y=0 live_target=6 files_nav: scroll_y=0 max_scroll_y=0 pending=1 retry=8 generation=2 confirmed=False textual=8.2.8. Timeout remains 5.0s. URL: https://github.com/sase-org/sase/actions/runs/40879308061/job/123474405005 . The other candidate, scheduled 40825968742 at dd59c28f44c7e5fc83cc75188ca58b710d4f32f7, also contains the fix and lists no watched failure, but individual watched-node execution was not established and is not counted as passing proof. ci_proof_runs=two is NOT satisfied. This is existing epic/task work, not a new follow-up. Reopened sase-1ou.6.1 per the approved plan recurrence branch; sase-1a7 and sase-1ou.6 stay open. Need investigate why enabling trailing reserve leaves max_scroll_y=0, not merely wait for a virtual_size change that never arrives. Preserve assertions, 5s timeout, generation ownership, hidden-paged guard, and manual-scroll behavior; no baseline suppression. The previous loaded-loop max_scroll_y=0 failures are now reproduced in the required CI environment and cannot be dismissed as unrelated.

[2026-10-29T15:05:58Z · sase-1ou.6.land--1] Durable CI failure evidence: file:explicit:c6f1c46fbe473d24b4235abb (candidate SHA ancestry, all Python job summaries, exact watched-node traceback and diagnostic). Use sase artifact read to consume it. The failure is in the first spread navigation wait before the visible-paged restore itself, so investigate trailing-reserve/extent publication rather than treating the test name as evidence of a paged restore defect. Source starting points: decks/_panel_spread_files_scroll.py::_cycle_files_spread and _on_files_scroll_extent; prompt_panel/_section_view.py::enable_section_layout_reserve and get_content_height; files_spread.py::_publish_section_layout. No production or tracked test files changed in this continuation.

[2026-10-29T20:17:24Z · sase-1ou.6.1] PROPOSED FOLLOW-UP: just check d25f8e01 NEW test_start_monitor_kills_a_supervisor_that_never_writes_the_ack_marker assert 6==1 — we did not touch monitor; lastfailed already listed it; isolated rerun still 6==1; already noted on sase-1pj.3 / sase-1pj.2.1.4. KNOWN import-budget 2845 vs 2844 has +0 sase.* delta vs merge-base (sase-1ic lineage); KNOWN supervisor-env is sase-1pg; KNOWN view-leak witness 01564beb; FLAKY contract_manifest. None keep this Files-spread phase open.

[2026-10-29T20:17:49Z · sase-1ou.6.1] Reserve remeasure fix for CI max_scroll_y=0: paged→spread already enables trailing reserve so cycle_card enable() was a no-op and paint retries never grew extent. Bust width-only height cache, viewport-height fallback, refresh_section_layout_reserve when already enabled and when apply sees short extent. Unfixed probe: scroll_y=0 live_target=6 max_scroll_y=0 pending=1 retry=8 reserve=0 reserve_on=True real_h=26. Isolated 50/50 both venvs (3.14/8.0.1 and 3.12/8.2.8) on trailing_reserve_remeasures, visible_paged_restore, stalled_navigation_resumes, superseding_navigation, files_ctrl_j. Loaded decks/ -n6 +48 spinners 5/5 both venvs. sase tool run d25f8e01 lint green; Files-spread tests not among failures. Verdict new_failures is 1 NEW monitor ack 6==1 (untouched, lastfailed pre-existing, isolated still fails, sase-1pj.3) plus 3 KNOWN (import budget +0 delta, view leak, sase-1pg) and 1 FLAKY contract_manifest. epic-symbols clean. sase-1a7 and sase-1ou.6 left open.

## Dependencies

- **Blocks:** [sase-1ou.6](sase-1ou.6.md) ◐ · ⧖ 2026-10-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ou.6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.6.1/README.md) | [sase-1ou.6.1](sase-1ou.6.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`aaa88b0`](https://github.com/sase-org/sase/commit/aaa88b002679ac9b12a5cdc4244426daa469011a) | fix(ace-tui): resume stalled Files spread navigation on scroll-extent growth | [sase-1ou.6.1](sase-1ou.6.1.md) | 2026-10-28 19:11:09 EDT |
| sase | [`2e68053`](https://github.com/sase-org/sase/commit/2e68053dab2fc560107a882a99f747e6de28761f) | fix(tui): remeasure Files spread reserve when already enabled | [sase-1ou.6.1](sase-1ou.6.1.md) | 2026-10-29 16:20:28 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ou.6.1][1] | Need full description and notes | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.6.1/README.md

<!-- sase:referenced-by:end -->
