# Bead: sase-1n8.4 — sase: reclaim the starter's cargo target when its monitor settles

[Bead Pages](../README.md) / [sase-1n8](README.md) / sase-1n8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.96` · **Assignee:** `sase-1n8.4` · **Size:** medium
**Created:** 2026-10-20 06:53:00 EDT · **Closed:** 2026-10-20 08:54:34 EDT
**Plan:** [202610/host\_completion\_loop\_and\_disk\_churn.md](https://github.com/sase-org/sase--plans/blob/main/202610/host_completion_loop_and_disk_churn.md)

## Previously Closed

> ↺ Closed 2026-10-20T11:18:40Z · done
>
> (none)
>
> Reopened 2026-10-20T11:24:22Z by `sase bead open`

## Description

monitor-scratch-reclaim: during monitor settlement, remove the unheld starter cargo-targets dir through the Rust-owned reaper, leaving agent-tmp to the backstop.

## Notes

[2026-10-20T11:18:40Z · sase-1n8.4] Reviewed landed commit 25d14fae6c; focused monitor settlement and scratch cleanup test modules passed via sase tool run (11.1s). Epic-symbol whitelist is clear.

[2026-10-20T11:24:27Z · sase-1n8.4] Reopened: cleanup read launch_scratch_key from the monitor artifacts dir, which never records it. Production settlement would no-op. Will read from monitor_starter_artifacts_dir as the design specified.

[2026-10-20T11:25:33Z · sase-1n8.4] PROPOSED FOLLOW-UP: Reuse one cargo-targets directory across an agent session so monitor cycles rebuild incrementally instead of minting a fresh 2.5 GB target each turn.

[2026-10-20T11:28:20Z · sase-1n8.4] Verified: settlement reads launch_scratch_key from monitor_starter_artifacts_dir; monitor-only keys, missing starter, missing dir, held/incomplete, joined, and agent-tmp cases pass (30 tests in test_monitor_proc_settlement.py and test_run_agent_runner_scratch_cleanup.py). Epic-symbols clear.

[2026-10-20T12:22:22Z · sase-1n8.4] Current checkout includes the original implementation (25d14fae6c), but not the starter-metadata correction recorded in note #4. proc_adapter still passes the monitor artifacts dir to read_recorded_scratch_key and the test fixture stores the key on the monitor. Completing this bounded remainder with realistic starter/monitor fixtures and regression verification; no child epic is needed.

[2026-10-20T12:25:28Z · sase-1n8.4] Regression evidence: with production-shaped starter/monitor fixtures, the old code failed the starter-target removal and monitor-only-key cases (ToolRun 3b7ddb7c09d224bc7bc6ce1a79b4f506). After reading launch_scratch_key from monitor_starter_artifacts_dir, all 33 monitor-settlement and runner-scratch tests pass (ToolRun a6c14844e3fb88a1e77ec33bb849842d), including repeated settlement, held/incomplete observations, joined monitors, missing/invalid starter metadata and agent-tmp preservation. Required just check is running as ToolRun d7a40a3f5b996d546fd556c8f25bde95.

[2026-10-20T12:54:00Z · sase-1n8.4] PROPOSED FOLLOW-UP: Existing TUI import-budget overage (sase-1ic) — just check ToolRun d7a40a3f5b996d546fd556c8f25bde95 failed test_tui_app_import_stays_under_startup_budget with 3523 modules vs strict cap 3522. Clean base e77280c873 reproduces the exact count/assertion in ToolRun cf5463d2246c284cb1499b8da06cce7f; this phase adds no imports. Corroborates sibling phase sase-1n8.3 note #1.

[2026-10-20T12:54:06Z · sase-1n8.4] PROPOSED FOLLOW-UP: Refresh stale contract manifest — test_contract_manifest_matches_marker_selection fails because tests/test_github_actions_release_steward.py is absent from tests/contract_manifest.txt. Exact failure reproduces on clean base e77280c873 in ToolRun cf5463d2246c284cb1499b8da06cce7f after failing just check d7a40a3f5b996d546fd556c8f25bde95. Corroborates sibling phase sase-1n8.3 note #1; not caused by the starter scratch lookup fix.

[2026-10-20T12:54:11Z · sase-1n8.4] PROPOSED FOLLOW-UP: Existing publication bounded-drain flakes (sase-xo) — broad check d7a40a3f5b996d546fd556c8f25bde95 failed test_blocked_render_is_bounded_and_leaves_the_request_queued at 15.63s after git index-lock backoff and test_after_a_blocked_render_a_later_drain_retries_and_succeeds at its 5s publication timeout. Both pass on clean base (cf5463d2246c284cb1499b8da06cce7f) and the unchanged restored phase tree (ad80406f165af08b0818f407e67768b8). Existing sase-xo evidence describes the same lock/backoff failure; no new bead created.

[2026-10-20T12:54:34Z · sase-1n8.4] Verified starter metadata lookup correction with regressions that fail on the old code; all 33 monitor-settlement and runner-scratch tests pass. Cleanup preserves agent-tmp, held/incomplete scratch, joined monitors, and missing/invalid starter metadata, and repeated settlement is harmless. Required just check d7a40a3f5b996d546fd556c8f25bde95 passed all lint/validation gates and 56920 tests; its four failures are two identical clean-base defects (cf5463d2246c284cb1499b8da06cce7f) and two existing publication-drain flakes passing on base and unchanged restored tree (ad80406f165af08b0818f407e67768b8). Recorded PROPOSED FOLLOW-UP notes with existing owners; no epic-symbol entries remain.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1n8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1n8.4/README.md) | [sase-1n8.4](sase-1n8.4.md) | 1 |
| [bbugyi200.athena.sase-1n8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1n8.4/README.md) | [sase-1n8.4](sase-1n8.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`25d14fa`](https://github.com/sase-org/sase/commit/25d14fae6c39fbea6cc43eb86984475c7a8aacea) | feat(monitor): reclaim starter cargo targets on settlement | [sase-1n8.4](sase-1n8.4.md) | 2026-10-20 07:09:21 EDT |
| sase | [`379040e`](https://github.com/sase-org/sase/commit/379040e699e50e283bc72e7d598541206c6b29d3) | fix(monitor): read starter metadata when reclaiming cargo targets | [sase-1n8.4](sase-1n8.4.md) | 2026-10-20 08:55:42 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1n8.4][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1n8.4.md

<!-- sase:referenced-by:end -->
