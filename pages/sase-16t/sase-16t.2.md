# Bead: sase-16t.2 — Wildcard parity, pin bump, pushdown guard, and docs in sase

[Bead Pages](../README.md) / [sase-16t](README.md) / sase-16t.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pq.md) · **Assignee:** `sase-16t.2` · **Size:** small
**Created:** 2026-09-23 08:23:31 EDT · **Closed:** 2026-09-23 10:38:27 EDT
**Plan:** [202609/artifact\_link\_jumps.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_jumps.md)

## Description

host-glob: move the sase-core CI pin past the wildcard commit, mirror the semantics in the Python reference evaluator with parity tests, keep glob values out of Agents-tab index pushdown, and document wildcards in the query language reference and field hints.

## Notes

[2026-09-23T13:10:30Z · sase-16t.2] PROPOSED FOLLOW-UP: symvision flags unused public class ExpandedLaunchSegments in src/sase/agent/launch_cwd_segments.py (from refactor commit cfac28d15); just check red on clean tree, unrelated to host-glob

## Dependencies

- **Depends on:** [sase-16t.1](sase-16t.1.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16t.4](sase-16t.4.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16t.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16t.2/README.md) | [sase-16t.2](sase-16t.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f37f1dd`](https://github.com/sase-org/sase/commit/f37f1dd480202d5eeead8aa04f8b0808504b8613) | feat(query): wildcard parity, pin bump, pushdown guard, and docs (sase-16t.2, verification pending) | [sase-16t.2](sase-16t.2.md) | 2026-09-23 09:18:34 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16t.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16t.2/README.md

<!-- sase:referenced-by:end -->
