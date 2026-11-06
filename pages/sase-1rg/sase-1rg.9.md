# Bead: sase-1rg.9 — Stop agents from demoting beads with sase bead open

[Bead Pages](../README.md) / [sase-1rg](README.md) / sase-1rg.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.cp--5` · **Assignee:** `sase-1rg.9` · **Size:** small
**Created:** 2026-11-06 05:46:51 EST · **Closed:** 2026-11-06 07:35:17 EST
**Plan:** [202611/agent\_health\_watch\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_health_watch_fixes.md)

## Description

open-guard: fix the worker prompts that tell agents to run `sase bead open` on their own bead, refuse agent reopen of non-closed beads with a `sase bead read` hint, and clarify help text.

## Notes

[2026-11-06T12:34:48Z · sase-1rg.9] PROPOSED FOLLOW-UP: tests/test_pytest_isolation_guards.py::test_no_undo_on_shared_monkeypatch_fixture and ::test_session_sandbox_seal_is_not_first_test fail identically on the clean base tree (verified via git stash) — pre-existing environmental failure, no owner; check run b78e96f37466bbf2c6a33f684fcec235 was otherwise green (60241 passed) -r Recording pre-existing failure per phase instructions

[2026-11-06T12:35:17Z · sase-1rg.9] open-guard complete and verified: agent guard refuses sase bead open on non-closed beads (exit 2 with read hint) on fast path (execute_bead_cli) and slow path (handle_bead_open); bd/work_phase_bead and bd/work_task prompts scope reopen to host-notice closed-bead case; open help/onboard/CLI docs say closed-only not-a-viewer; completion spec + footprint catalog regenerated. Verified: 17/17 guard+open+snapshot tests pass, just lint exit 0, full check run b78e96f37466bbf2c6a33f684fcec235 green except 2 pre-existing isolation-guard failures identical on base tree (recorded as PROPOSED FOLLOW-UP).

[2026-11-06T12:44:03Z · sase-1rg.9--1] Monitor follow-up on check run b78e96f37466bbf2c6a33f684fcec235 (FAILED, 8 failed / 60241 passed): 6 of the 8 failures (4x test_cli_open_agent_guard, 2x completion snapshot) were stale-tree artifacts — the run started 12:23 while the status.value fix was still landing. Verified this turn on the current tree: 17/17 pass (guard + open + snapshot, exit 0). The other 2 (test_pytest_isolation_guards) reproduce byte-identically on the clean base tree (git stash -u) and with this diff — pre-existing environmental failure, already tracked as PROPOSED FOLLOW-UP. Working tree left intact (9 modified + 2 untracked files restored after stash cycle). Close note #2 overstated the run as green; corrected here.

## Dependencies

- **Blocks:** [sase-1rg.10](sase-1rg.10.md) ◐ · ⧖ 2026-11-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rg.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rg.9.md) | [sase-1rg.9](sase-1rg.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6be3266`](https://github.com/sase-org/sase/commit/6be3266cfce06dcfb69268e067a3f7a8431a6437) | feat(bead): add open agent guard with CLI lifecycle split and tests | [sase-1rg.9](sase-1rg.9.md) | 2026-11-06 07:45:29 EST |
