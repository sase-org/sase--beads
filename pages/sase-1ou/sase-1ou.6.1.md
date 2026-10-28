# Bead: sase-1ou.6.1 — Remove the stall in Files spread navigation and make CI timeouts diagnosable

[Bead Pages](../README.md) / [sase-1ou.6](sase-1ou.6.md) / sase-1ou.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ou.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ou.land.md) · **Assignee:** `sase-1ou.6.1` · **Size:** medium
**Created:** 2026-10-28 17:04:15 EDT · **Closed:** 2026-10-28 19:09:38 EDT
**Plan:** [202610/files\_spread\_ci\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202610/files_spread_ci_landing.md)

## Description

files-landing: rebuild the CI-like Python 3.12 / Textual 8.2.8 environment, prove with a deterministic real-widget test that pending Files navigation stalls once its bounded refresh-retry chain runs out after the last layout publish, make navigation resume on scroll-extent change instead, add state to the anchor-wait timeout message, and prove it with isolated and loaded loops in both Textual versions.

## Notes

[2026-10-28T23:09:38Z · sase-1ou.6.1] Stall fixed + timeouts diagnosable. Fix: DeckPanel watches Files VerticalScroll virtual_size; _on_files_scroll_extent re-arms pending nav via _reschedule_files_scroll_after_layout (bounded chain keeps 8-hop backstop, re-arms per extent change). wait_for_anchor_scroll gains diagnose param; Files call sites pass describe_files_nav (scroll_y/max/pending/retry/generation/confirmed + textual version); timeout and success condition unchanged. No assertions/timeouts/baselines changed; no baseline entries; sase-1a7 left open. Evidence: new test_stalled_navigation_resumes_on_scroll_extent_growth FAILS before (anchor_wait scroll_y=0 target=6 max=54 pending=1 retry=8) PASSES after. Isolated 50x each, both venvs (3.14/8.0.1 and scratch 3.12/8.2.8 outside repo per plan): regression 50/50+50/50, ctrl_j 50/50+50/50, superseding 50/50+50/50. Loaded decks-dir -n6 +48 spinners: 4/5 clean per venv; each single flake shows max_scroll_y=0 at timeout (extent never grew in-window under contention) and the same signature reproduces on the clean base tree (ctrl_j + late_layout fail there too), so it is the known pre-existing wait-vs-layout race, not a regression; scheduled Full CI proof stays with the land agent. sase tool run check: ruff/mypy/test-waits/changelog/terminology/docs/scoped-tests green; only 9 KNOWN pre-existing symvision in untouched files (verdict no_new_failures). Hypothesis confirmed, no course change. Untried plan routes (random order, pinned-CPU tui run, full non-visual pinned set) available to land agent if wanted.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ou.6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ou.6.1/README.md) | [sase-1ou.6.1](sase-1ou.6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`aaa88b0`](https://github.com/sase-org/sase/commit/aaa88b002679ac9b12a5cdc4244426daa469011a) | fix(ace-tui): resume stalled Files spread navigation on scroll-extent growth | [sase-1ou.6.1](sase-1ou.6.1.md) | 2026-10-28 19:11:09 EDT |
