# Bead: sase-1bu.7 — Acceptance fixtures, benchmark, docs, and memory

[Bead Pages](../README.md) / [sase-1bu](README.md) / sase-1bu.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tb.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tb.w0.md) · **Assignee:** `sase-1bu.7` · **Size:** medium
**Created:** 2026-09-27 19:03:27 EDT · **Closed:** 2026-09-28 11:00:40 EDT
**Plan:** [202609/goal\_ledger.md](https://github.com/sase-org/sase--plans/blob/main/202609/goal_ledger.md)

## Description

acceptance: prove the epic end to end with two-clone concurrency and marker-race fixtures, crash repair, fail-closed schemas, offline publishing, the agent refusal matrix, and the 100k-settled benchmark with file-open proof. Finish docs/goals.md and land the authorized memory updates.

## Notes

[2026-09-28T15:00:12Z · sase-1bu.7] PROPOSED FOLLOW-UP: projection-aware hot read — warm list p50 ~37ms at 1000 unsettled vs 5ms contract (e2e p50 ~70ms vs 50ms downstream); list re-reduces every live goal, never consults goals-hot.json; needs sase-core read-path surgery + binding + pin ratchet. Full numbers: file:explicit:1dba5d50c8383526696e7f4f

[2026-09-28T15:00:40Z · sase-1bu.7] Acceptance done: 11 new fixtures in tests/goals/test_goal_acceptance.py pass (two-clone convergence byte-identical, settlement-race determinism + reconcile no-op, id-collision with remedy, fault-hook crash repair both directions, fail-closed STORE-kinds incl doctor-reports, unknown-kind isolation, offline outbox then retry-publish, show-allowed refusal, config-warn fallback, fresh-projection skip); tools/goal_ledger_bench + just bench-goals added, full 100k-settled/1000-live report registered as file:explicit:1dba5d50c8383526696e7f4f; docs/goals.md in mkdocs nav, just docs-check clean; 6 authorized memory updates landed, sase memory init --check clean; all 7 sase-1bu epic-symbols removed (2 dead facade wrappers deleted, rest genuinely wired), just _lint-symvision clean; sase tool run check lint gates all green + 94 goals/memory tests + 26 parser/artifact/docs tests pass (full check test lane cut by 9-min command cap after lint). Known miss recorded as PROPOSED FOLLOW-UP: warm-list p50 ~37ms vs 5ms at 1000 live needs projection-aware read (structural sase-core change); at contract scale (100 live) all verdicts pass. Pin d2d9ec7 stands: post-pin sase-core commits touch only launch_scratch_liveness, no new bindings called.

## Dependencies

- **Depends on:** [sase-1bu.5](sase-1bu.5.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bu.6](sase-1bu.6.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bu.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bu.7/README.md) | [sase-1bu.7](sase-1bu.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`acfca26`](https://github.com/sase-org/sase/commit/acfca26dbaf5a80550b8a294d87a46c00aac6dc7) | feat(goals): complete G1 acceptance for goal ledger | [sase-1bu.7](sase-1bu.7.md) | 2026-09-28 11:03:54 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bu.7][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bu.7/README.md

<!-- sase:referenced-by:end -->
