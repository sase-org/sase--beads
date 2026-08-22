# Bead: sase-s2.3 — Prove the combined approval-to-launch lifecycle

[Bead Pages](../README.md) / [sase-s2](README.md) / sase-s2.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0an](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0an.md) · **Assignee:** `sase-s2.3` · **Size:** small
**Created:** 2026-08-22 12:48:40 UTC · **Closed:** 2026-08-22 15:08:43 UTC
**Plan:** [202608/plan\_approval\_launch\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202608/plan_approval_launch_reliability.md)

## Description

reliability-integration: exercise tale approval, sidecar link finalization, epic approval during a developer update, and exhaustive repository checks together so neither fix leaves a false failed agent or a duplicate durable mutation.

## Notes

[2026-08-22T14:43:16Z · sase-s2.3] Added combined approval-to-launch regressions (tale delayed-archive + coder link linear history; epic code-swap wait then one DAG). Stubbed host archives in leftover commit-approval tests that had no project identity. Focused gate/archive/swap/monitor/epic suites passed; race tests passed 3x with inverted scheduling. No --epic-symbol leftovers. Handing just check-full to a monitor.

[2026-08-22T15:08:17Z · sase-s2.3--1] PROPOSED FOLLOW-UP: Recurate tests/contract_manifest.txt for tests/test_ratchet_core_window_source_normalization.py — just check-full failed only on tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection (36063 passed, 12 skipped). That file carries pytest.mark.contract and landed in c718da911 after the last manifest refresh (8c1acbfa5); this phase did not change the contract marker set. Out of scope for sase-s2.3: do not refresh the manifest here.

[2026-08-22T15:08:43Z · sase-s2.3--1] Verified combined approval-to-launch regressions: tale delayed-archive + coder artifact-link linear history; historical two-writer rebase conflict; inverted-scheduling archive publication; epic code-swap wait then one DAG. Stubbed host-owned archives in leftover commit-approval tests without project identity. Focused gate/archive/swap/monitor/epic suites passed; race tests passed 3x with inverted scheduling. No --epic-symbol leftovers. just check-full: 36063 passed, 12 skipped; only failure is out-of-scope tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection (stale manifest after tests/test_ratchet_core_window_source_normalization.py became contract-marked in c718da911; this phase did not change the marker set; recorded as PROPOSED FOLLOW-UP).

## Dependencies

- **Depends on:** [sase-s2.1](sase-s2.1.md) ✓ · ⧖ 2026-08-22
- **Depends on:** [sase-s2.2](sase-s2.2.md) ✓ · ⧖ 2026-08-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s2.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-s2.3.md) | [sase-s2.3](sase-s2.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`62538c4`](https://github.com/sase-org/sase/commit/62538c4b0c5fbe8bafb786e0e51e52b3f086975e) | test(plan): prove combined approval-to-launch lifecycle (sase-s2.3) | [sase-s2.3](sase-s2.3.md) | 2026-08-22 15:10:43 UTC |
