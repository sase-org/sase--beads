# Bead: sase-1lh.7.5.1 — Finish strict check-mode recovery and enforce the retry deadline

[Bead Pages](../README.md) / [sase-1lh.7.5](sase-1lh.7.5.md) / sase-1lh.7.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1lh.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.land.md) · **Assignee:** `sase-1lh.7.5.1` · **Size:** medium
**Created:** 2026-10-16 20:23:08 EDT · **Closed:** 2026-10-16 21:31:16 EDT
**Plan:** [202610/finish\_recapture\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_recapture_release.md)

## Description

recapture-contract: repair internal-error masking, targeted-run false failures, unbounded retry subprocesses, and the Python 3.12 help assertion without changing update-mode salvage or exact golden matching.

## Notes

[2026-10-17T01:31:06Z · sase-1lh.7.5.1--1] PROPOSED FOLLOW-UP: tests/test_launch_approval_tui.py::test_tui_launch_approval_dispatch_failure_records_failed_response fails identically on clean base (fake_launch missing extra_env kwarg from fae5cf5076); owned by sibling phase release-integration via sase-1lw scope

[2026-10-17T01:31:16Z · sase-1lh.7.5.1--1] recapture-contract done: strict scope-aware check recovery (internal-error/exit-disagreement/collection-mismatch/skip/structural-omission stay failures; targeted runs exempt from full-scope root demand), retry exit/protocol validation, wall-clock deadline carried into governed subprocess with bounded reap and manifest, py3.12 help assertion fixed. Verified: 147 focused tests pass (check_recapture 33 incl. exec_timeout, verify/salvage/base 71, apply_*/ci-workflow 43); full sase tool run check cc7049d97217d3d6c0d219a7533de415 has 1 NEW failure in test_launch_approval_tui dispatch_failure which reproduces identically on clean base and belongs to sase-1lw/release-integration scope (recorded as PROPOSED FOLLOW-UP). No epic-symbols leftovers.

## Dependencies

- **Blocks:** [sase-1lh.7.5.2](sase-1lh.7.5.2.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lh.7.5.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.5.1.md) | [sase-1lh.7.5.1](sase-1lh.7.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`499c825`](https://github.com/sase-org/sase/commit/499c825cb931953efb2af6c49d7d504e04e8c0bc) | fix(visual): enforce strict check-mode recovery and retry deadline | [sase-1lh.7.5.1](sase-1lh.7.5.1.md) | 2026-10-16 21:33:07 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1lh.7.5.1--1][1] | Need phase scope, design, notes, and DECISIONS | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lh.7.5.1.md

<!-- sase:referenced-by:end -->
