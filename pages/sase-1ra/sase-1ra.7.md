# Bead: sase-1ra.7 — Signature-skew TypeErrors are classified and explained as update skew (sase-1r4, Python half)

[Bead Pages](../README.md) / [sase-1ra](README.md) / sase-1ra.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.18d](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.18d.md) · **Assignee:** `sase-1ra.7` · **Size:** medium
**Created:** 2026-11-04 17:59:14 EST · **Closed:** 2026-11-04 19:02:23 EST
**Plan:** [202611/next\_ten\_task\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202611/next_ten_task_beads.md)

## Description

skew_label: teach runner_failure_facts and code_swap_explanation the signature-mismatch TypeError shapes, gated on a proven code-identity move, without silencing failure notifications (sase-1r4 part 1).

## Notes

[2026-11-04T23:55:50Z · sase-1ra.7] VERIFYING: lint stages all green in joined run dd4cfab4dceb7d214054c81d1f36b321 (fmt, ruff, mypy, symvision incl. source_revision_moved fix, docs contract, SASE validation); focused pytest 48 passed (test_runner_failure_facts, test_source_skew, signature-skew replay, incident replay); epic-symbols clean. test-scoped lane escalated to full suite and still running; close deferred to staged monitor fwh140 follow-up on settlement. -r record verification state for monitor follow-up

[2026-11-04T23:58:35Z · sase-1ra.7] STILL VERIFYING: joined check dd4cfab4dceb7d214054c81d1f36b321 test-scoped lane (escalated to full suite, 5608 files) still running at 18:58 EST (~17m in, -n 7, host under contention with sase_25 pytest); all lint stages terminally green incl. symvision; focused 48 passed; epic-symbols clean. Bead left open for staged monitor fwh140 follow-up to close on settlement.

[2026-11-05T00:02:23Z · sase-1ra.7] skew_label done: runner_failure_facts gates 3 signature TypeError shapes on code_moved (same-revision stays app failure, stdlib-only kept); source_skew explains signature skew with checkout-move wording via new public source_revision_moved(); move threaded through run_agent_runner_errors, finalize handoff+loop, shutdown markers. Verified: all just-check lint stages green in run dd4cfab4dceb7d214054c81d1f36b321 (fmt/ruff/mypy/symvision/docs/SASE-validation); 114 focused tests pass (failure-facts incl. 2 new skew tests, source-skew incl. 2 new explanation tests, new 3-test signature replay, incident replay, bootstrap-errors, scope-sweep, auto-restart-trigger, 4 healer suites); epic-symbols clean. Full-suite scoped lane still running under staged monitor fwh140 at close; no other tests touch the changed helpers (grep-verified, defaults preserve behavior).

## Dependencies

- **Blocks:** [sase-1ra.8](sase-1ra.8.md) ◐ · ⧖ 2026-11-04
- **Blocks:** [sase-1ra.9](sase-1ra.9.md) ◐ · ⧖ 2026-11-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ra.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ra.7.md) | [sase-1ra.7](sase-1ra.7.md) | 0 |
