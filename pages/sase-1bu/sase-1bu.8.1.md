# Bead: sase-1bu.8.1 — Ledger correctness fixes in sase-core

[Bead Pages](../README.md) / [sase-1bu.8](sase-1bu.8.md) / sase-1bu.8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1bu.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bu.land.md) · **Assignee:** `sase-1bu.8.1` · **Size:** medium
**Created:** 2026-09-28 11:36:43 EDT · **Closed:** 2026-09-28 12:30:41 EDT
**Plan:** [202609/goal\_ledger\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/goal_ledger_landing_fixes.md)

## Description

core-fixes: fix sase-core goal append/reduce/read/projection/doctor/probe defects (unknown-id refusals, id normalization, stable criterion ids, criteria validation, corrupt-file isolation, projection rebuild and header preservation, reopen/claim reducer gaps, fixture and basis wire fidelity, a real I/O probe) with Rust tests.

## Notes

[2026-09-28T16:30:41Z · sase-1bu.8.1] core-fixes done: all 13 plan items implemented with Rust tests (unknown-id refusals incl. no-write, id normalization, stable criterion ids, edit validation incl. title_empty/outcome_empty/criterion_not_found/no_changes, corrupt-file isolation, corrupt-projection rebuild, doctor header preservation, reopen/claim reducer gaps, basis-always + 26-char fixtures, real I/O probe with 1000+10 negative control, render allow_threads + doctor binding test). Verified: sase tool run check green in sase-core (run b1d6b6c6), sase just install rebuilt, tests/goals/ + test_sync_remote_push.py 101 passed with no sase test changes, epic-symbols empty

## Dependencies

- **Blocks:** [sase-1bu.8.2](sase-1bu.8.2.md) ✓ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bu.8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bu.8.1/README.md) | [sase-1bu.8.1](sase-1bu.8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@32d80d6`](https://github.com/sase-org/sase-core/commit/32d80d6fbcc0fe952c904614a082167b5cafa914) | fix(goals): land G1 ledger correctness fixes for core-fixes phase | [sase-1bu.8.1](sase-1bu.8.1.md) | 2026-09-28 12:32:00 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bu.8.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bu.8.1/README.md

<!-- sase:referenced-by:end -->
