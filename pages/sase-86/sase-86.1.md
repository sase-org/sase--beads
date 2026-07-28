# Bead: sase-86.1 — Host worker-token budget

[Bead Pages](../README.md) / [sase-86](README.md) / sase-86.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-86.1` · **Size:** medium
**Created:** 2026-07-20 14:59:54 UTC
**Plan:** [202607/fast\_test\_suite.md](https://github.com/sase-org/sase--plans/blob/main/202607/fast_test_suite.md)

## Description

'Host worker-token budget' section: replace whole-suite gate slots with a crash-safe host-global pool of xdist worker tokens so a solo run gets ~2x more workers and concurrent runs share capacity fairly without head-of-line queueing.

## Notes

Implemented a UID-scoped crash-safe pytest worker-token pool with CPU/available-memory budgeting, atomic floor/ceiling grants, exact raw-xdist and SASE_PYTEST_WORKERS accounting, inherited exec locks, diagnostics, docs, and focused coverage. Verification: 62 focused gate/runner tests passed; governed runner plus raw numeric/auto xdist smoke tests passed; three-process grants were 4, 2, then 4 after release; SIGKILL reacquisition passed; SASE_TEST_GATE_SLOTS=12 SASE_PYTEST_WORKERS=8 just check passed end to end.

## Dependencies

- **Blocks:** [sase-86.4](sase-86.4.md) ✓
- **Blocks:** [sase-86.6](sase-86.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-86.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-86.1/README.md) | [sase-86.1](sase-86.1.md) | 1 |
| [bbugyi200.athena.sase-86.1--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-86.1.md#member-code) | [sase-86.1](sase-86.1.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`8599baa`](https://github.com/sase-org/sase/commit/8599baa3a93e6c1c4a8c1f05b6f0c014b64aa322) | feat(test): add host-global pytest worker budget (sase-86.1) | [sase-86.1](sase-86.1.md) | 2026-07-20 16:07:28 |
