# Bead: sase-zs.7 — Bound clone concurrency and stop stranding workspaces on transient failure

[Bead Pages](../README.md) / [sase-zs](README.md) / sase-zs.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0k6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0k6.md) · **Assignee:** `sase-zs.7` · **Size:** medium
**Created:** 2026-09-12 09:44:55 EDT · **Closed:** 2026-09-12 11:58:25 EDT
**Plan:** [202609/github\_network\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202609/github_network_resilience.md)

## Description

materialization: cap concurrent remote clones so parallel launches stop saturating the uplink, and let the agent runner degrade or requeue instead of hard-failing and holding a numbered workspace.

## Notes

[2026-09-12T15:57:52Z · sase-zs.7] PROPOSED FOLLOW-UP: Retire or isolate the known global-state leak detector full-parallel flake - just check for sase-zs.7 hit tests/test_global_state_leak_detector.py::test_snapshot_includes_live_config_token_refresh_threads, which is already listed in tests/reproducible_flake_baseline.txt and passed isolated.

[2026-09-12T15:58:25Z · sase-zs.7] Implemented bounded host remote clone admission and transient setup materialization release path. Verified focused pytest for SDD clone retry, runner lifecycle, and workspace identity passed; just fmt and symvision passed; just check passed all pre-test stages and full scoped pytest failed only the known baseline flake tests/test_global_state_leak_detector.py::test_snapshot_includes_live_config_token_refresh_threads, which passed isolated; epic-symbols reported no entries.

## Dependencies

- **Depends on:** [sase-zs.2](sase-zs.2.md) ✓ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zs.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zs.7/README.md) | [sase-zs.7](sase-zs.7.md) | 0 |
