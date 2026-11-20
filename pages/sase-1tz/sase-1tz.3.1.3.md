# Bead: sase-1tz.3.1.3 — Defer and retry scheduler jobs that overlap a code swap

[Bead Pages](../README.md) / [sase-1tz.3.1](sase-1tz.3.1.md) / sase-1tz.3.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.3.md) · **Assignee:** `sase-1tz.3.1.3` · **Size:** medium
**Created:** 2026-11-20 09:19:05 EST · **Closed:** 2026-11-20 11:29:28 EST
**Plan:** [202611/defects\_wire\_swap\_telegram\_bundles\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202611/defects_wire_swap_telegram_bundles_triage.md)

## Description

swap_chop_guards: the code-swap writer records a durable last-swap stamp. The chop runner does not start scripts while a writer is live, and it treats a missing script within a short post-swap grace as inhibited. A run that overlapped a swap and died of SIGBUS or a swap-skew import error is recorded as a skipped retry, not an error. Flip the chop xfails.

## Notes

[2026-11-20T16:29:04Z · sase-1tz.3.1.3] IMPLEMENTED (swap_chop_guards). (1) Last-swap stamp: new src/sase/dev_update/code_swap_stamp.py writes ~/.sase/locks/code-swap-last.json {op, pid, started_at, completed_at, generation} atomically on every writer release, before the holder payload clears (so a prober always sees the live writer or the finished swap). It is written even when the swap body raised, never when the lock was refused or SASE_DISABLE_CODE_SWAP_LOCK=1. code_swap_writer_lock (both branches) and the stdlib installer SwapLock.release (tools/_sase_install_run.py, mirrored as LAST_SWAP_FILENAME / record_last_swap) share one generation counter, pinned by tests/sase_install/test_last_swap_stamp_parity.py. Readers treat a missing or corrupt stamp as no swap. (2) The chop runner no longer starts any script while a live writer holds the lock. (3) A missing script within CODE_SWAP_GRACE_SECONDS=120 of the last completed swap is an inhibited skip; after the window it is missing_script again. (4) Post-exit: a nonzero exit that overlapped a swap (writer live at exit, or last swap started<=finish and completed>start) and died of SIGBUS (-7) or matched runner_failure_facts skew patterns (via capture_failure_facts on the diagnostic output_excerpt) becomes status=skipped, skip_reason=inhibited, advances_cadence=False, checkpoint action_failed. It keeps exit_code and subprocess_diagnostic and has no error, so nothing reaches the error ring. Guards live in src/sase/axe/chop_swap_guard.py. (5) All 5 chop xfails in tests/dev_update/test_swap_repro_chops.py are flipped. The only remaining reproducer xfail is the swap_launch_guards (d) BeforeSpawnCallback one. (6) Docs: scheduler-jobs.md Job Run History, plus plugins-update.md code-swap lock. This also fixed swap_repro follow-up #5, the stale code-swap.lock path, which is now code-swap-v2.lock. (7) tools/swap_overlap_census now scans only the reason of skipped run records and counts them as deferred_script/deferred_start/deferred_exit, so a deferred SIGBUS is not counted as a sigbus failure.

[2026-11-20T16:29:15Z · sase-1tz.3.1.3] FOR swap_launch_guards (sase-1tz.3.1.4): "the swap grace from swap_chop_guards" is sase.dev_update.code_swap_stamp.CODE_SWAP_GRACE_SECONDS. read_last_code_swap() returns .generation for the long-lived-process approach (record at start, restart when it advances). recent_code_swap() covers the post-swap window. Symvision forced the stamp dataclass and path helper private (_LastCodeSwap, _last_code_swap_path) because nothing outside the file names them yet. If that phase needs the type name, make it public with that real consumer. Import these lazily, as chop_swap_guard does: the sase.dev_update package __init__ is heavy.

[2026-11-20T16:29:28Z · sase-1tz.3.1.3] Verified: sase tool run check dbdeb3f9 succeeded (every fmt/lint gate including mypy and symvision, docs build and links, scoped tests over 534 files). Focused suites pass: test_code_swap_stamp (stamp on release, generation, raise, disabled, refused, corrupt, grace, overlap), test_last_swap_stamp_parity (installer and sase share the file, shape, and generation, and the pypi, failed-pypi, and dev pipelines all stamp), test_axe_chop_swap_guard (no start under a writer, grace in and out, SIGBUS and missing-binding overlap retries, writer live at exit, and the controls: earlier swap, unrelated failure). The reproducer chop xfails are flipped: 10/10 pass. dev_update, sase_install, chop runner, and lumberjack suites: 585 passed, plus the 1 expected swap_launch_guards xfail. No epic symbols.

## Dependencies

- **Depends on:** [sase-1tz.3.1.2](sase-1tz.3.1.2.md) ✓ · ⧖ 2026-11-20
- **Blocks:** [sase-1tz.3.1.4](sase-1tz.3.1.4.md) ◐ · ⧖ 2026-11-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.3.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.3/README.md) | [sase-1tz.3.1.3](sase-1tz.3.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3ae6b09`](https://github.com/sase-org/sase/commit/3ae6b09b72d8efed932981077cbb2266daa631fd) | feat(axe): defer and retry scheduler jobs that overlap a code swap | [sase-1tz.3.1.3](sase-1tz.3.1.3.md) | 2026-11-20 11:30:49 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1tz.3.1.2][1] | Check sibling phase state and epic decisions before swap_repro work | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.3.1.2/README.md

<!-- sase:referenced-by:end -->
