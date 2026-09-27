# Bead: sase-1b2.3 — FinalizerNodeView detail - attempts, operations, evidence, and runs

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.3` · **Size:** medium
**Created:** 2026-09-27 05:49:32 EDT · **Closed:** 2026-09-27 07:10:54 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

core-run-view-detail: extend the projection with attempts, operations (schema-v1 and legacy commit records), steps, carriage-return-collapsed live tails, typed evidence and headline selection, attempt-scoped diagnostic dedupe, warning counts, failure reason lines, and multi-run node composition. Prove it with commit, command and plugin fixtures.

## Notes

[2026-09-27T11:10:37Z · sase-1b2.3] PROPOSED FOLLOW-UP: Node aggregate and per-run duration_seconds are named in plan section 3.4 Response but have no defined source (result/journal carry no timing; only op records do) — needs a follow-up bead to specify and implement run/node timing.

[2026-09-27T11:10:54Z · sase-1b2.3] core-run-view-detail done in sase-core: attempts from result+journal events, operations from schema-v1/legacy commit records plus journal op events, C3 steps (64KiB tolerant), CR-collapsed live tails, typed evidence with SHA>URL>bead>exit_code headline, attempt-scoped diagnostic dedupe with superseded downgrade, warning counts, failure-reason lines, D10 supersede node aggregate with number-ordered runs. Proved by 10 new fixtures (commit success+deferral, command 2-attempt failure, plugin acme open-pr, 3-run session, CR/tail and truncation units). 37 run_view tests green; sase tool run check green; epic-symbols clean; pin move left to run-view-adapter.

## Dependencies

- **Blocks:** [sase-1b2.12](sase-1b2.12.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1b2.2](sase-1b2.2.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.3/README.md) | [sase-1b2.3](sase-1b2.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@e53d7a5`](https://github.com/sase-org/sase-core/commit/e53d7a5d34b5677d56380d07ce51fbbfdbe5c1ce) | feat(finalizer): implement core-run-view-detail projection content | [sase-1b2.3](sase-1b2.3.md) | 2026-09-27 07:12:39 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 1 |
| read-by | [agent:sase-1b2.3][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.3/README.md

<!-- sase:referenced-by:end -->
