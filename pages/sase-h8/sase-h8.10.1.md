# Bead: sase-h8.10.1 — Actually implement the clock phase that sase-h8.5 closed without landing

[Bead Pages](../README.md) / [sase-h8.10](sase-h8.10.md) / sase-h8.10.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-h8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.land/README.md) · **Assignee:** `sase-h8.10.1` · **Size:** medium
**Created:** 2026-08-08 10:56:22 EDT · **Closed:** 2026-08-08 11:16:21 EDT
**Plan:** [202608/flake\_class\_residue.md](https://github.com/sase-org/sase--plans/blob/main/202608/flake_class_residue.md)

## Description

clock: drive `EventLoopStallWatchdog` from an injectable time source so the five F2 `test_stall_watchdog.py` nodes plus `test_nested_pause_requires_final_resume_before_detection` produce hitch and stall episodes deterministically, restore exact episode counts in place of the `>= 1` tolerances two prior fixes installed, keep one real-timer end-to-end test, and move `test_contract_set_serial_runtime_stays_within_budget` off wall clock now that sase-h8.7's F6 fix unblocked it.

## Notes

[2026-08-08T15:16:21Z · sase-h8.10.1] Implemented injectable monotonic clock and _poll_once seam for EventLoopStallWatchdog; converted targeted watchdog F2 tests and nested pause test to fake-clock exact event sequences; kept real-timer watchdog coverage. Verified: .venv/bin/python -m pytest -q tests/ace/tui/util/test_stall_watchdog.py (17 passed); SASE_TEST_SELECTION_HEALTH_DISABLED=1 .venv/bin/python -m pytest -q -p no:randomly tests/test_contract_manifest.py::test_contract_set_serial_runtime_stays_within_budget (1 passed, guard already normalized child CPU so unchanged); just test-contention -- tests/ace/tui/util/test_stall_watchdog.py (0 node failures across 3 repeats); just check (passed).

[2026-08-08T15:17:39Z · sase-h8.10.1] Verified pytest -q tests/ace/tui/util/test_stall_watchdog.py, contract budget with SASE_TEST_SELECTION_HEALTH_DISABLED=1, just test-contention -- tests/ace/tui/util/test_stall_watchdog.py, and just check.

## Dependencies

- **Blocks:** [sase-h8.10.2](sase-h8.10.2.md) ◐ · ⧖ 2026-08-08
- **Blocks:** [sase-h8.10.4](sase-h8.10.4.md) ◐ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h8.10.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h8.10.1/README.md) | [sase-h8.10.1](sase-h8.10.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2e9e1a2`](https://github.com/sase-org/sase/commit/2e9e1a29c388f864604756ec7d7972fbc791ab3d) | fix(tui): make stall watchdog tests deterministic | [sase-h8.10.1](sase-h8.10.1.md) | 2026-08-08 11:18:29 EDT |
