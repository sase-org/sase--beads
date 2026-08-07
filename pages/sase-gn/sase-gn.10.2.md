# Bead: sase-gn.10.2 — Non-mocked close regression coverage and the core pin bump

[Bead Pages](../README.md) / [sase-gn.10](sase-gn.10.md) / sase-gn.10.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-gn.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.land/README.md) · **Assignee:** `sase-gn.10.2` · **Size:** medium
**Created:** 2026-08-07 00:13:46 EDT · **Closed:** 2026-08-07 01:19:26 EDT
**Plan:** [202608/snooze\_close\_corruption.md](https://github.com/sase-org/sase--plans/blob/main/202608/snooze_close_corruption.md)

## Description

snooze-close-regression: pin the sase-core release carrying the fix and cover both close call sites against a real bead store, closing the mocking gap that let the corruption ship.

## Notes

[2026-08-07T05:19:26Z · sase-gn.10.2] Bumped sase-core-rs to >=0.19.0,<0.20.0 in pyproject.toml (0.19.0 is now published on PyPI; release-plz PR #91 merged) and refreshed uv.lock to 0.19.0; pulled the linked sase-core checkout to master so the dev build matches the pin. Updated the hardcoded floor in tests/test_sase_core_rs_telemetry_smoke_tool.py::test_declared_minimum_tracks_pyproject_dependency from 0.18.4 to 0.19.0. Added tests/test_bead/test_snooze_close_regression.py: five real-store tests with no project mock, covering the gate close/ready/re-snooze side effects, 'sase bead close' on a snoozed bead, and an event-stream replay (issues.jsonl deleted, record re-derived). Each asserts the cold reload through the bead_list binding, not just the call. Verified these are genuine regression tests by rebuilding the binding at the pre-fix core commit 386d357: the three close-path tests fail with 'validation: Only snoozed issues can carry snooze metadata'; all five pass against the fix. just check-full green: every lint gate plus the full suite (26k+ tests, 0 failed).

## Dependencies

- **Depends on:** [sase-gn.10.1](sase-gn.10.1.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-gn.10.5](sase-gn.10.5.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gn.10.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gn.10.2/README.md) | [sase-gn.10.2](sase-gn.10.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5b3f349`](https://github.com/sase-org/sase/commit/5b3f3494b9488719acacfa067d570fdef4d05f61) | build(deps): raise sase-core-rs floor to 0.19.0 and cover the snooze close path against a real store | [sase-gn.10.2](sase-gn.10.2.md) | 2026-08-07 01:20:07 EDT |
