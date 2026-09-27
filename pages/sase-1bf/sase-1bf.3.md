# Bead: sase-1bf.3 — Dead-launch backstop pass and liveness-aware pressure

[Bead Pages](../README.md) / [sase-1bf](README.md) / sase-1bf.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.1d` · **Assignee:** `sase-1bf.3` · **Size:** medium
**Created:** 2026-09-27 14:23:35 EDT
**Plan:** [202609/bounded\_agent\_scratch.md](https://github.com/sase-org/sase--plans/blob/main/202609/bounded_agent_scratch.md)

## Description

dead-launch-reap: the housekeeping reaper removes launch-keyed scratch that no live process holds after a short grace, pressure pruning becomes liveness-aware with a realistic minimum entry size, and defaults and docs move with it.

## Notes

[2026-09-27T22:19:27Z · sase-1bf.3] Phase work complete in working tree (uncommitted): Rust dead-launch backstop + liveness-aware pressure in sase-core crates/sase_core/src/managed_tmp.rs (wire 3->4, dead_launch request/result fields, reap_dead_launch, apply_pressure_liveness) with 8 new unit tests (40/40 managed_tmp pass) + binding round-trip test in sase_core_py config/tests.rs; Python adapter/config/chops/docs in sase repo (15 files + new tests/test_managed_tmp_reaper_dead_launch.py, 11 tests). Python suites green: 115 passed across reaper/runner/chop/disk/schema/roots/sandbox files, incl. updated chop-contract counters. Handoff finding: monitor/gate follow-ups mint a FRESH scratch key via launch_spawn._managed_agent_scratch_env (fresh timestamp per spawn_detached_child), so no pending-gate key special-casing was needed; docs record this. LAND SEQUENCING: sase side now requires wire 4; CI builds the core from sase-core-revision.txt (still pinned pre-change), so land sase-core first, then ratchet the pin (precedent: b2a10778e6 bumped the wire without moving the pin; ratchet follows). sase-core full just-check gate still fails on PRE-EXISTING clippy-1.95 drift in untouched files (see PROPOSED FOLLOW-UP citing sase-1an); my files are clippy-clean.

[2026-09-27T22:19:49Z · sase-1bf.3] PROPOSED FOLLOW-UP: sase-core just-check clippy gate fails on clean-tree toolchain drift (stable 1.95 flags repeat().take, redundant closures, collapsible ifs in agent_runtime, launch_scratch_liveness, provider_usage, tool_run store, etc.) — corroborates sase-1an; my dead-launch files add zero new clippy errors

## Dependencies

- **Depends on:** [sase-1bf.1](sase-1bf.1.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bf.2](sase-1bf.2.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bf.6](sase-1bf.6.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bf.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bf.3.md) | [sase-1bf.3](sase-1bf.3.md) | 0 |
