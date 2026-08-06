# Bead: sase-fp.4 — just check / just check-full split

[Bead Pages](../README.md) / [sase-fp](README.md) / sase-fp.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tn/README.md) · **Assignee:** `sase-fp.4` · **Size:** small
**Created:** 2026-08-05 20:56:19 EDT · **Closed:** 2026-08-05 22:49:36 EDT
**Plan:** [202608/test\_suite\_tier1.md](https://github.com/sase-org/sase--plans/blob/main/202608/test_suite_tier1.md)

## Description

check-split: repoint `just check` at the scoped lane, add `just check-full` carrying today's exhaustive behaviour, and update docs/development.md, README.md, CONTRIBUTING.md, and the CI guard tests.

## Notes

[2026-08-06T02:49:14Z · sase-fp.4] PROPOSED FOLLOW-UP: tests/test_contract_manifest.py::test_contract_set_serial_runtime_stays_within_budget and tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout fail reproducibly under just test/just check-full (12-worker xdist) but pass cleanly in isolation (-p no:xdist) — resource-contention flakiness unrelated to sase-fp.4 diff, worth a task bead to make them contention-tolerant or move off the parallel lane.

[2026-08-06T02:49:36Z · sase-fp.4] Verified: just check now runs whole-repo lint gates + just test-scoped (no suite-gate lease); just check-full carries the prior exhaustive test lane. Updated docs/development.md (new 'Diff-scoped checks' section), README.md, CONTRIBUTING.md, docs/rust_backend.md to point pre-submit guidance at check-full. Added tests/test_justfile_lint.py coverage (check/check-full recipes exist, check ends in test-scoped, check-full ends in test, both share an identical non-test gate list) and tests/test_github_actions_ci.py::test_ci_never_runs_the_diff_scoped_test_lane. Ran the 32 new/existing Justfile+CI guard tests (all pass) and two full 'just check-full' runs end-to-end (25648 passed, 7 skipped each run); the only failures were 2 pre-existing tests (bead-lock contention timing, contract-manifest runtime budget) that reproduce under 12-worker xdist but pass in isolation and are untouched by this diff — logged as a PROPOSED FOLLOW-UP note.

## Dependencies

- **Depends on:** [sase-fp.3](sase-fp.3.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fp.7](sase-fp.7.md) ◐ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fp.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fp.4/README.md) | [sase-fp.4](sase-fp.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`515ef3a`](https://github.com/sase-org/sase/commit/515ef3a48e6911a4c8eb9fe9499f09bceb14fa5b) | build(justfile): split \`just check\` into a scoped agent lane and \`just check-full\` | [sase-fp.4](sase-fp.4.md) | 2026-08-05 22:50:30 EDT |
