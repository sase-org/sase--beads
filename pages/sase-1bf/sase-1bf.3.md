# Bead: sase-1bf.3 — Dead-launch backstop pass and liveness-aware pressure

[Bead Pages](../README.md) / [sase-1bf](README.md) / sase-1bf.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.1d` · **Assignee:** `sase-1bf.3` · **Size:** medium
**Created:** 2026-09-27 14:23:35 EDT · **Closed:** 2026-09-27 19:27:35 EDT
**Plan:** [202609/bounded\_agent\_scratch.md](https://github.com/sase-org/sase--plans/blob/main/202609/bounded_agent_scratch.md)

## Description

dead-launch-reap: the housekeeping reaper removes launch-keyed scratch that no live process holds after a short grace, pressure pruning becomes liveness-aware with a realistic minimum entry size, and defaults and docs move with it.

## Notes

[2026-09-27T22:19:27Z · sase-1bf.3] Phase work complete in working tree (uncommitted): Rust dead-launch backstop + liveness-aware pressure in sase-core crates/sase_core/src/managed_tmp.rs (wire 3->4, dead_launch request/result fields, reap_dead_launch, apply_pressure_liveness) with 8 new unit tests (40/40 managed_tmp pass) + binding round-trip test in sase_core_py config/tests.rs; Python adapter/config/chops/docs in sase repo (15 files + new tests/test_managed_tmp_reaper_dead_launch.py, 11 tests). Python suites green: 115 passed across reaper/runner/chop/disk/schema/roots/sandbox files, incl. updated chop-contract counters. Handoff finding: monitor/gate follow-ups mint a FRESH scratch key via launch_spawn._managed_agent_scratch_env (fresh timestamp per spawn_detached_child), so no pending-gate key special-casing was needed; docs record this. LAND SEQUENCING: sase side now requires wire 4; CI builds the core from sase-core-revision.txt (still pinned pre-change), so land sase-core first, then ratchet the pin (precedent: b2a10778e6 bumped the wire without moving the pin; ratchet follows). sase-core full just-check gate still fails on PRE-EXISTING clippy-1.95 drift in untouched files (see PROPOSED FOLLOW-UP citing sase-1an); my files are clippy-clean.

[2026-09-27T22:19:49Z · sase-1bf.3] PROPOSED FOLLOW-UP: sase-core just-check clippy gate fails on clean-tree toolchain drift (stable 1.95 flags repeat().take, redundant closures, collapsible ifs in agent_runtime, launch_scratch_liveness, provider_usage, tool_run store, etc.) — corroborates sase-1an; my dead-launch files add zero new clippy errors

[2026-09-27T23:26:55Z · sase-1bf.3--1] PROPOSED FOLLOW-UP: just check symvision gate fails on pre-existing private import _segment_section_identity in ace/tui prompt_panel (imported by decks/panel_view_deferred.py); both files untouched by this phase (diff has zero matches), HEAD already defines it private

[2026-09-27T23:27:14Z · sase-1bf.3--1] PROPOSED FOLLOW-UP: just check test-scoped escalates to FULL_SUITE (src-data-asset rule, 4466 files from default_config/schema/docs changes) and timed out after 1h at test-scoped stage (signal 15); focused suites pass, no phase action

[2026-09-27T23:27:35Z · sase-1bf.3--1] Verified: 59 focused pytest pass (dead_launch/reaper/pressure/config/disk/chop-contract), 40/40 sase_core managed_tmp pass, ruff+mypy clean on touched files; just check fmt/ruff/mypy/validation pass, symvision fail + full-suite timeout are pre-existing/unrelated (untouched files, FULL_SUITE escalation)

## Dependencies

- **Depends on:** [sase-1bf.1](sase-1bf.1.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bf.2](sase-1bf.2.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bf.6](sase-1bf.6.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bf.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bf.3.md) | [sase-1bf.3](sase-1bf.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c2eb318`](https://github.com/sase-org/sase/commit/c2eb318d8818f47390d80cfe8f07f5cd87cfe51e) | feat(managed-tmp): dead-launch backstop pass and liveness-aware pressure (sase-1bf.3) | [sase-1bf.3](sase-1bf.3.md) | 2026-09-27 19:39:41 EDT |
