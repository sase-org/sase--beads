# Bead: sase-1m3.12 — Cross-surface parity, budgets, and real-data verification

[Bead Pages](../README.md) / [sase-1m3](README.md) / sase-1m3.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.1s.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.1s.linker.w0.md) · **Assignee:** `sase-1m3.12` · **Size:** small
**Created:** 2026-10-16 22:05:25 EDT · **Closed:** 2026-10-19 15:44:12 EDT
**Plan:** [202610/sase\_stats\_project.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_stats_project.md)

## Description

acceptance: add the CLI-to-TUI parity and registry option-map tests, verify invariants and coverage on this machine's real data, measure the performance budgets, run the full visual suite, and record follow-ups.

## Notes

[2026-10-19T17:26:32Z · sase-1m3.12] PROPOSED FOLLOW-UP: Investigate warm project_stats query latency — measured 3,158 ms for output+runs and 1,128 ms for code on this machine versus 150 ms and 500 ms budgets; source timing and breakdown need review.

[2026-10-19T17:26:56Z · sase-1m3.12] PROPOSED FOLLOW-UP: Add the skipped statistics decision record after human review; this plan was auto-decided no-human-reviewed, and DECISIONS prohibits editing memory during this phase.

[2026-10-19T17:27:10Z · sase-1m3.12] PROPOSED FOLLOW-UP: Track the epic §22 ideas: the other seven CLI/Markdown views, fleet-wide Runs, churn/growth/monthly sparklines/latest release, cost/tokens, --as-of, config role globs, CSV/auto formats, non-deadlocking file-history batches, declared_by reuse in sase-1l2, and a stable plan id if rename churn proves material.

[2026-10-19T17:32:50Z · sase-1m3.12] PROPOSED FOLLOW-UP: Capture and inspect a live Statistics → Projects screenshot and measure TUI first paint. `sase screenshot` twice timed out while the Admin Center stayed on Machines; the key sequence did not activate Statistics.

[2026-10-19T19:10:33Z · sase-1m3.12] PROPOSED FOLLOW-UP: Triage ToolRun 34ef20961546adbafe2e61663f862d68 failures: 2 NEW tests reproduced on clean HEAD 0f2052be6a (`test_changed_reply_invalidates_hint_document_and_mappings`, `test_contract_manifest_matches_marker_selection`); `test_hint_mode_keeps_typed_artifact_refs_semantic` failed in check/current isolation but passed on clean HEAD. No changed files touch those areas; 15 KNOWN and 1 FLAKY also reported.

[2026-10-19T19:43:53Z · sase-1m3.12--1] PROPOSED FOLLOW-UP: Resolve the partial TUI visual run: test_agents_decks_left_right_search_committed_png_snapshot failed capture after three attempts, leaving its golden unverified; investigate the two ignored agents_session_panel_level_1/2 captures and rerun the visual suite for complete evidence.

[2026-10-19T19:44:12Z · sase-1m3.12--1] Completed CLI/TUI parity and registry option-map coverage; real-data invariants and budgets were measured, with budget misses recorded as follow-ups. just fix-tui-screenshots exited 0 but reported partial: 17 updated goldens were visually inspected, 1097 unchanged, and one committed-search snapshot failed after retries so stale pruning was skipped; follow-up recorded. Existing follow-ups for the skipped memory decision, live screenshot, and check triage remain. No epic-symbol entries remained.

## Dependencies

- **Depends on:** [sase-1m3.1](sase-1m3.1.md) ✓ · ⧖ 2026-10-16
- **Depends on:** [sase-1m3.10](sase-1m3.10.md) ✓ · ⧖ 2026-10-16
- **Depends on:** [sase-1m3.11](sase-1m3.11.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.12](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.12.md) | [sase-1m3.12](sase-1m3.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4e5b7d2`](https://github.com/sase-org/sase/commit/4e5b7d2eb6feff3d0c95f9f71d91ccbb494607cf) | feat(stats): complete project stats acceptance checks | [sase-1m3.12](sase-1m3.12.md) | 2026-10-19 15:45:51 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1m3.12--1][1] | Verify the assigned phase closed with visual outcome and follow-ups recorded | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1m3.12.md

<!-- sase:referenced-by:end -->
