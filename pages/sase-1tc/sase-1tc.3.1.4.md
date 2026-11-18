# Bead: sase-1tc.3.1.4 — Resume unfinished batches and honor clan kills

[Bead Pages](../README.md) / [sase-1tc.3.1](sase-1tc.3.1.md) / sase-1tc.3.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tc.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.3.md) · **Assignee:** `sase-1tc.3.1.4` · **Size:** medium
**Created:** 2026-11-17 19:16:09 EST · **Closed:** 2026-11-18 05:51:01 EST
**Plan:** [202611/chop\_launch\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202611/chop_launch_recovery.md)

## Description

recovery: reconcile pending batches before routine guards, thread shutdown through workers, preserve lifecycle and once-per state, record explicit clan cancellation, and emit durable notices. See Phase recovery.

## Notes

[2026-11-18T10:51:01Z · sase-1tc.3.1.4] Recovery complete and verified: shared recover_pending_chop_batches entry point reconciles pending batches before routine guards (tick + manual), ChopStopSignal threads SIGTERM through workers without new dispatch, lifecycle finalizer and run-history pruning retain resumable batches (paused guard), explicit clan-generation cancellation persists before TUI member expansion across marked/kill-all/cleanup-panel/custom/focused paths, deduplicated run logs + notifications emitted and _state_inflight distinguishes journaled resume from unjournaled drops. New tests/axe/test_axe_chop_batch_recovery.py (5 tests) plus existing batch/lifecycle suites pass; sase tool run check d95a84a1 green end-to-end (all lints incl. symvision, scoped lane escalated to full suite per Justfile rule, exit 0). Justfile: dropped 2 now-properly-used sase-1tc.3.1 whitelist rows (ChopBatchError, replay_ordinary_chop_batch), added 3 for new inter-phase API (ChopBatchRecoveryResult, collect_spawn_observations, has_unfinished_chop_batch).

## Dependencies

- **Depends on:** [sase-1tc.3.1.3](sase-1tc.3.1.3.md) ✓ · ⧖ 2026-11-17
- **Blocks:** [sase-1tc.3.1.5](sase-1tc.3.1.5.md) ◐ · ⧖ 2026-11-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.3.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.3.1.4.md) | [sase-1tc.3.1.4](sase-1tc.3.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b8c9f6c`](https://github.com/sase-org/sase/commit/b8c9f6c6aa101546a21539dcafc17b20ccdcdaf5) | feat(axe): add chop batch pause-resume recovery, clan cancellation, and durable notices | [sase-1tc.3.1.4](sase-1tc.3.1.4.md) | 2026-11-18 05:54:13 EST |
