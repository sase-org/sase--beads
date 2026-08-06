# Bead: sase-gj.1 — Per-test-file duration table recorded by the full lane

[Bead Pages](../README.md) / [sase-gj](README.md) / sase-gj.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ue](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ue/README.md) · **Assignee:** `sase-gj.1` · **Size:** medium
**Created:** 2026-08-06 16:01:17 EDT · **Closed:** 2026-08-06 16:41:59 EDT
**Plan:** [202608/scoped\_lane\_latency.md](https://github.com/sase-org/sase--plans/blob/main/202608/scoped_lane_latency.md)

## Description

timings: record per-test-file wall seconds from full-lane runs into the host-local store and expose an `estimate_serial_seconds()` the selector can call, with an explicit no-data answer.

## Notes

[2026-08-06T20:41:28Z · sase-gj.1] PROPOSED FOLLOW-UP: the real table shows tests/test_contract_manifest.py alone costs 127.6s serial of the suite total 4268.4s — the `budget` phase should check whether the contract set, which every scoped run includes unconditionally, already eats over half a 232s budget.

[2026-08-06T20:41:59Z · sase-gj.1] timings landed measured and inert. New tests/_test_selection_timings.py (table store, merge, estimate_serial_seconds with explicit no-data answers) + tests/_test_selection_timings_plugin.py (per-test-file wall-second sink), armed by tools/run_pytest on the full lanes and on scoped runs; manifest schema 4->5 adds a timings block (estimate, coverage fraction, table SHA/mtime identity), with an escalated run recorded as reason=escalated rather than 0.0. 40 new unit tests in tests/test_test_selection_timings.py. Verified end to end against the real host store: a real 'just test' full lane wrote a 2346-of-2349-file table totalling 4268.4s serial (top file tests/test_contract_manifest.py at 127.6s), and a second full lane merged into it newest-wins. No decision consults the estimate in this phase. just check-full green (exit 0, 26085 passed).

[2026-08-06T20:42:50Z · sase-gj.1] verified: just check-full green (exit 0, 26085 passed); real full-lane timings table written and merged newest-wins

## Dependencies

- **Blocks:** [sase-gj.2](sase-gj.2.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gj.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gj.1/README.md) | [sase-gj.1](sase-gj.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6cf5a94`](https://github.com/sase-org/sase/commit/6cf5a94d7ce95c5e80e5f924bd58bddec13ecfb4) | feat(test-selection): record per-test-file timings from full-lane runs | [sase-gj.1](sase-gj.1.md) | 2026-08-06 16:44:06 EDT |
