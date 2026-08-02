# Bead: sase-e9.2 — Close the ACE visual convergence gap

[Bead Pages](../README.md) / [sase-e9](README.md) / sase-e9.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rw](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rw/README.md) · **Assignee:** `sase-e9.2` · **Size:** medium
**Created:** 2026-08-02 14:12:26 UTC · **Closed:** 2026-08-02 15:11:10 UTC
**Plan:** [202608/just\_test\_contention\_flakes.md](https://github.com/sase-org/sase--plans/blob/main/202608/just_test_contention_flakes.md)

## Description

visual: stop Textual animations from running under PNG snapshot tests and teach the convergence helper to treat pending animations as unfinished work, so a starved app cannot present five identical mid-animation frames.

## Notes

[2026-08-02T14:30:21Z · sase-e9.2] PROPOSED FOLLOW-UP: Make the fakey retry-state visual setup wait load-tolerant — under the gate-disabled 26-worker/two-CPU harness, test_real_fakey_retry_countdown_png_snapshot timed out in FakeyRetryHarness.wait_for_retry_state after its fixed 5s budget before AcePage/capture; the slow-tools snapshot passed and no PNG mismatch or convergence timeout occurred.

[2026-08-02T14:31:39Z · sase-e9.2] FOLLOW-UP RESOLVED IN PHASE: aligned the scoped retry visual tests with their existing 60s fakey barrier budget, replacing the 5s helper default that failed before AcePage started under the 26-worker/two-CPU harness.

[2026-08-02T14:52:27Z · sase-e9.2] PROPOSED FOLLOW-UP: Diagnose bead CLI lock-wait regression under extreme host I/O contention — just check failed tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout after 85.94s while /proc/pressure/io full pressure was roughly 15–20%; this is unrelated to ACE visual convergence.

[2026-08-02T15:11:10Z · sase-e9.2] Verified 13/13 visual-idle tests, including animation disablement on a running AcePage and pending animator gating/diagnostics; both reproduced PNG snapshots passed with 26 workers pinned to two CPUs (2 passed in 82.08s) without golden changes. Final just check passed all static/validation gates and 25,377 tests, including both scoped retry visuals; its sole failure was the twice-reproduced unrelated bead CLI lock-wait contention test recorded as a PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-e9.3](sase-e9.3.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e9.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e9.2/README.md) | [sase-e9.2](sase-e9.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`adfa350`](https://github.com/sase-org/sase/commit/adfa3504327d8251e8606bfb213ad53926145189) | test(visual): stabilize PNG convergence under contention | [sase-e9.2](sase-e9.2.md) | 2026-08-02 15:12:45 |
