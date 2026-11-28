# Bead: sase-1vn.4.1.2 — Read-only zombie report and TUI integration

[Bead Pages](../README.md) / [sase-1vn.4.1](sase-1vn.4.1.md) / sase-1vn.4.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1vn.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vn.4.md) · **Assignee:** `sase-1vn.4.1.2` · **Size:** medium
**Created:** 2026-11-27 20:17:45 EST · **Closed:** 2026-11-27 22:15:23 EST
**Plan:** [202611/zombie\_epic\_liveness.md](https://github.com/sase-org/sase--plans/blob/main/202611/zombie_epic_liveness.md)

## Description

reporting: consume the shared predicate in a read-only bead zombies command and existing stranded-work TUI surfaces, advance the core pin, and capture the current zombie inventory without launching or closing anything.

## Notes

[2026-11-28T03:14:52Z · sase-1vn.4.1.2] PROPOSED FOLLOW-UP: tests/tool/test_admission_processes.py::test_limit_two_with_four_runs_never_overlaps_more_than_two flaked once during the full just check lane under host load (load ~20) and passes 5/5 in isolation plus a green module run; related area already tracked by sase-1ve. No product code touches admission.

[2026-11-28T03:15:23Z · sase-1vn.4.1.2] Reporting phase verified: sase bead zombies (compact|json, current project default, -a all-projects) consumes bead_zombie_plan_tree_snapshot + zombie_plan_evaluate with batched stranded member facts; TUI beads pane warms the same predicate off-thread (badge + close-time sentence, stranded precedence preserved). Core pin advanced to 91380657 and dev wheel rebuilt with both bindings. Tests: 10 new CLI/collector tests, 3 presentation tests, 5 cache tests, 1 TUI detail regression — all green. just check (run 7d9af4ce): all lint gates pass; test lane 63905 passed with 2 failures — import-budget overrun fixed by lazy imports (test green) and one admission-concurrency load flake green 5/5 in isolation (recorded as proposed follow-up). Live sase report 2026-11-28T03:12Z: 33 zombies / 6 unknown / 2 owned / 90 not-zombie; sase-zu and sase-zn still zombies; artifact file:explicit:95fcc65660f2a5ea7525e495 noted on sase-1vn.4. No bead armed, claimed, launched, closed, or reopened. A redundant staged rust-install monitor (zqmtve) may run a cache-hit rebuild after this turn.

## Dependencies

- **Depends on:** [sase-1vn.4.1.1](sase-1vn.4.1.1.md) ✓ · ⧖ 2026-11-27
- **Blocks:** [sase-1vn.4.1.3](sase-1vn.4.1.3.md) ✓ · ⧖ 2026-11-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vn.4.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vn.4.1.2.md) | [sase-1vn.4.1.2](sase-1vn.4.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`96e87d5`](https://github.com/sase-org/sase/commit/96e87d598425639b43fd066bd51d5e9b0fd3526e) | feat(bead): add read-only zombie-plan report and TUI integration | [sase-1vn.4.1.2](sase-1vn.4.1.2.md) | 2026-11-27 22:18:35 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1vn.4.1.land][1] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1vn.4.1.land/README.md

<!-- sase:referenced-by:end -->
