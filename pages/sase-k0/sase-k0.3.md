# Bead: sase-k0.3 — Settle bead gates from sase bead close

[Bead Pages](../README.md) / [sase-k0](README.md) / sase-k0.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yk](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yk/README.md) · **Assignee:** `sase-k0.3` · **Size:** medium
**Created:** 2026-08-12 10:58:54 EDT · **Closed:** 2026-08-12 12:09:05 EDT
**Plan:** [202608/task\_gate\_convergence.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_gate_convergence.md)

## Description

close_settle: have the close command cancel each closed task bead's pending gate right after the store mutation commits, so the existing notifications inotify watch refreshes ACE at once, and keep the added cost off closes that cannot have gates.

## Notes

[2026-08-12T16:09:05Z · sase-k0.3] Implemented close_settle: handle_bead_close now settles each just-closed task bead's pending gate right after the store mutation commits. Added src/sase/bead/close_gate_settle.py (settle_closed_task_bead_gates: one find_pending_bead_gates scan across TASK_TRIAGE_KIND+BEAD_SNOOZE_KIND, cancels matches with reason=bead_closed, swallows already_answered/other errors). Wired via _settle_close_task_gates in cli_crud.py, gated on non-empty task-typed closed_ids|cascade_closed_ids so plan/phase closes and already-closed no-ops do zero filesystem work. Added tests/test_bead/test_cli_close_gate_settle.py (6 tests: ready-task task_triage cancel, snoozed-task bead_snooze cancel, no-gate no-op, plan close does zero scans, multi-bead close does exactly one scan, already_answered race is benign). just lint and just check both pass (check's scoped lane escalated to the full suite per core-identity-changed and still passed, 1685/1685 in tests/test_bead alone).

[2026-08-12T16:10:16Z · sase-k0.3] Implemented close_gate_settle: sase bead close now cancels pending task_triage/bead_snooze gates for closed task beads via a single find_pending_bead_gates scan, wired into handle_bead_close in cli_crud.py. Added 6 tests in test_cli_close_gate_settle.py covering ready/snoozed gate cancellation, no-gate no-op, zero-scan plan close, single-scan multi-bead close, and already_answered race handling. just lint and just check both pass (check escalated to full suite, still green).

## Dependencies

- **Depends on:** [sase-k0.1](sase-k0.1.md) ✓ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k0.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k0.3/README.md) | [sase-k0.3](sase-k0.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`875f67b`](https://github.com/sase-org/sase/commit/875f67b74da1e3829b9b2ec72be40df8e9be6726) | feat(bead): settle pending gates immediately on task bead close | [sase-k0.3](sase-k0.3.md) | 2026-08-12 12:11:34 EDT |
