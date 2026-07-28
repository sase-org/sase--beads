# Bead: sase-ak.4 — Surface waits that can never resolve

[Bead Pages](../README.md) / [sase-ak](README.md) / sase-ak.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ak.4` · **Size:** small
**Created:** 2026-07-28 21:05:43 UTC · **Closed:** 2026-07-28 22:10:49 UTC
**Plan:** [202607/tribe\_wait\_reference\_validation\_and\_display.md](https://github.com/sase-org/sase--plans/blob/main/202607/tribe_wait_reference_validation_and_display.md)

## Description

unresolvable-wait-surface: give already-parked reserved-tribe waits a distinct "this wait can never resolve" presentation in ACE so agents launched before the guard landed are diagnosable rather than silently pending.

## Notes

[2026-07-28T22:10:49Z · sase-ak.4] Implemented reserved tribe wait unresolvable ACE marker. Verified: focused pytest wait/render suites 97 passed; single reserved visual snapshot passed after inspecting/accepting the new PNG; just test-visual passed 367 passed, 1 skipped; just test passed 23282 passed, 7 skipped; git diff --check clean. just check ran fmt/lint through symvision/toobig but failed in unrelated SASE validation: provider skill files need init skills refresh and 202607/fix_ci_core_clippy_and_minimum.md has missing prompt/reverse-link errors.

## Dependencies

- **Depends on:** [sase-ak.1](sase-ak.1.md) ✓
- **Depends on:** [sase-ak.3](sase-ak.3.md) ✓
