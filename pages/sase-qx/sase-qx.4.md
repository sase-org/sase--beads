# Bead: sase-qx.4 — Fail-closed launch guard

[Bead Pages](../README.md) / [sase-qx](README.md) / sase-qx.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07o](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07o.md) · **Assignee:** `sase-qx.4` · **Size:** medium
**Created:** 2026-08-19 09:58:32 EDT · **Closed:** 2026-08-19 14:44:40 EDT
**Plan:** [202608/soft\_provider\_disables.md](https://github.com/sase-org/sase--plans/blob/main/202608/soft_provider_disables.md)

## Description

guard-core: enumerate the launch units one prompt will spawn, refuse before any spawn when a unit can only run on a hard-disabled provider, and accept an ACE-resolved unit bundle through the `sase run` request payload.

## Notes

[2026-08-19T18:43:04Z · sase-qx.4] PROPOSED FOLLOW-UP: tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift and test_current_structural_view_matches_checked_in_snapshot still fail on origin/master, unrelated to sase-qx.4 — reproduced with this phase stashed; needs just sync-completion-spec and a commit (same as sase-qx.2).

[2026-08-19T18:43:45Z · sase-qx.4] PROPOSED FOLLOW-UP: tests/test_global_state_leak_detector.py::test_snapshot_includes_live_config_token_refresh_threads failed once under the full just check-scoped xdist run (missing sase.config.core._live_config_token_refresh_threads in the snapshot) but passes cleanly in isolation — order/pollution flake, not caused by this phase.

[2026-08-19T18:44:40Z · sase-qx.4] Implemented the fail-closed launch guard per plan:202608/soft_provider_disables.md. plan_launch_units/blocked_launch_units enumerate expanded segments (repeat/alt slots as candidates) without consuming pool cursors; a unit is blocked only when every candidate is hard-disabled or unavailable and at least one is hard-disabled. launch_agents_from_cwd_impl refuses with DisabledProviderLaunchError (actionable Launch Control remedy) before name resolution/workspace claim/spawn, records the failed prompt, and fails open on unexpected guard errors. sase run accepts a strict launch_units payload and ignores it when force-reuse applies. 31 new tests pass. just check: all lint/mypy/symvision/toobig/SASE-validation green; Justfile epic-symbols for this phase are none (LaunchUnit/LaunchUnitCandidate/plan_launch_units/blocked_launch_units keyed to sase-qx.5). Full-suite escalation (Justfile) had 3 failures, all confirmed unrelated: 2 completion-spec snapshot drifts reproduced on master with this tree stashed, 1 leak-detector flake that passes in isolation.

[2026-08-19T18:46:09Z · sase-qx.4] Fail-closed launch guard: plan_launch_units/blocked_launch_units refuse a launch before spawn when every candidate of a unit is hard-disabled or unavailable and at least one is hard-disabled. 31 new tests; just check lint/mypy/symvision/toobig/SASE-validation green; no --epic-symbol leftovers on sase-qx.4.

## Dependencies

- **Depends on:** [sase-qx.2](sase-qx.2.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-qx.5](sase-qx.5.md) ◐ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qx.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qx.4/README.md) | [sase-qx.4](sase-qx.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`44415dd`](https://github.com/sase-org/sase/commit/44415dddd0904937d59d3c65fa6e5988bcb95bea) | feat(agent): refuse launches that can only run on a hard-disabled provider | [sase-qx.4](sase-qx.4.md) | 2026-08-19 14:47:47 EDT |
