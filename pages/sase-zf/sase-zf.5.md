# Bead: sase-zf.5 — Documentation rewrite and verification sweep

[Bead Pages](../README.md) / [sase-zf](README.md) / sase-zf.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0iy](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0iy.md) · **Assignee:** `sase-zf.5` · **Size:** small
**Created:** 2026-09-10 18:01:50 EDT · **Closed:** 2026-09-10 22:27:02 EDT
**Plan:** [202609/agents\_query\_unification.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_query_unification.md)

## Description

docs-and-sweep: rewrite the user docs for the unified dialect including the legacy-token migration table, refresh the help-modal syntax section and configuration reference, and run the final perf and visual snapshot sweep.

## Notes

[2026-09-11T02:20:54Z · sase-zf.5] PROPOSED FOLLOW-UP: Feature-flag lint gate is red for unrelated live flag bead sase-z5 — `just check` fails at tools/check_feature_flags because key `weighted_queue_capacity` has no registry definition; add the definition or close/fix that flag bead before expecting this workspace to pass the full default check.

[2026-09-11T02:27:02Z · sase-zf.5] Updated docs/help for agents-live query dialect; verified focused query/help tests, Agents help and filter-bar visual snapshots, trace smoke/view-hints perf scenarios, serial Agents j/k/clan benchmarks, remaining post-flag check gates, and diff-scoped tests (823 passed). Full just check is blocked before scoped tests by unrelated live flag bead sase-z5 missing registry definition for weighted_queue_capacity; recorded PROPOSED FOLLOW-UP on this phase.

## Dependencies

- **Depends on:** [sase-zf.4](sase-zf.4.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zf.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zf.5/README.md) | [sase-zf.5](sase-zf.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a53f4d0`](https://github.com/sase-org/sase/commit/a53f4d04e5fa8e45452a3e293d1edeee6188fc23) | docs(ace): document unified agents query syntax | [sase-zf.5](sase-zf.5.md) | 2026-09-10 22:28:25 EDT |
