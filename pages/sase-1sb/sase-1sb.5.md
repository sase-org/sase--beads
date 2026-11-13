# Bead: sase-1sb.5 — Fix patch-lock fd double close and edit-lock acquisition races

[Bead Pages](../README.md) / [sase-1sb](README.md) / sase-1sb.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bk.md) · **Assignee:** `sase-1sb.5` · **Size:** small
**Created:** 2026-11-11 17:38:54 EST · **Closed:** 2026-11-11 20:51:56 EST
**Plan:** [202611/security\_bug\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/security_bug_audit_fixes.md)

## Description

Two verified defects in src/sase/ace/patch/locking.py:

1. `patch_lock` (~lines 166-184): on lock timeout the `except BlockingIOError`
   branch runs `os.close(fd)` and raises `LockTimeoutError`, but the function's
   `finally` then runs `fcntl.flock(fd, LOCK_UN)` + `os.close(fd)` on the
   already-closed fd. Single-threaded this raises OSError(EBADF) from the finally,
   replacing LockTimeoutError so handlers keying on it (e.g.
   src/sase/ace/patch/duplicate_repair.py, src/sase/ace/hooks/persistence.py)
   misclassify the failure; multi-threaded (ACE runs these in worker threads) the
   fd number can be reused by another thread between the close and the finally,
   and the finally then unlocks/closes an unrelated descriptor. Fix: restructure
   so acquisition happens before the try whose finally owns cleanup (or drop the
   close from the timeout branch and make the finally the single owner); the
   timeout path must raise LockTimeoutError exactly once with no second close.

2. `acquire_edit_lock` / `is_edit_locked` (~lines 37-91): the lock file is
   created with a plain overwrite (no O_CREAT|O_EXCL), so two processes can both
   believe they own the edit lock; liveness uses `os.kill(pid, 0)`, so a recycled
   PID makes a stale lock look held and `wait_for_edit_lock_release` can poll for
   hours. Fix: create with O_CREAT|O_EXCL (retry after stale-lock cleanup),
   record PID plus process start time (or an equivalent boot-relative token), and
   treat a PID whose start time does not match as stale.

Tests: timeout path raises LockTimeoutError (not OSError) and leaves no dangling
fd (assert via os.fstat raising on the fd or fd-count accounting); concurrent
edit-lock acquisition admits exactly one owner; a stale lock with a recycled-PID
token is reclaimed.

## Notes

[2026-11-12T01:51:37Z · sase-1sb.5] PROPOSED FOLLOW-UP: Investigate intermittent TUI lifecycle test failure — tests/ace/tui/test_agents_tab_x_row_lifecycle_e2e.py::test_done_row_dismissed_without_signal_and_stays_hidden failed in check 9fc932a5c1882d437f428b27d2054f6d, then passed in an isolated rerun.

[2026-11-12T01:51:56Z · sase-1sb.5] Fixed patch-lock timeout cleanup and edit-lock ownership with exclusive creation and process-start tokens. 15 focused tests, Ruff, and targeted mypy pass. The broad check had one test teardown error from an earlier test version and one unrelated TUI failure that passed on isolated rerun; follow-up recorded.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sb.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sb.5/README.md) | [sase-1sb.5](sase-1sb.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6cdb74c`](https://github.com/sase-org/sase/commit/6cdb74c3e673c786a5d345985b1a9e9816e270d2) | fix(ace): make patch and edit locks race-safe | [sase-1sb.5](sase-1sb.5.md) | 2026-11-11 20:53:32 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1sb.5][1] | Verify the assigned phase is closed after implementation and test completion | 2 |
| read-by | [agent:sase-1sd.land][2] | Check sase-1sb.5 notes for the concurrent edit lock test | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sb.5/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sd.land/README.md

<!-- sase:referenced-by:end -->
