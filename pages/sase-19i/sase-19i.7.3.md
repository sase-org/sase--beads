# Bead: sase-19i.7.3 — Finish the remaining Node Finder open and broad-query budgets

[Bead Pages](../README.md) / [sase-19i.7](sase-19i.7.md) / sase-19i.7.3

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19i.7.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.land.md) · **Assignee:** `sase-19i.7.3.land`
**Created:** 2026-09-26 10:26:44 EDT
**Plan:** [202609/node\_finder\_remaining\_budgets.md](https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_remaining_budgets.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/node_finder_remaining_budgets.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_remaining_budgets.md

<!-- sase:links:end -->

## Description

The 2,000-node Node Finder meets the approved first-paint and refilter p95 budgets without changing navigation behavior.

## Notes

[2026-09-26T16:31:53Z · sase-19i.7.3.land] LAND REVIEW 2026-09-26: both phases are closed and their stitches are present (d1b72cfe5 facets, 221d72a13 exact-semantics snapshot cuts). Code matches the notes: per-open facet tables, single grouping-name read, facet fold filter, fused unmet walk, shared tree index, and the differential tests. Fresh official bench: open p50 94.75ms p95 569.11ms vs <50ms FAIL; narrow p95 3.03ms, broad p95 14.27ms, highlight p95 0.63ms PASS. Stage split: snapshot steady ~69-110ms with 400-600ms stalls, modal init ~1.2ms, first-paint drain best 22.5ms / p50 ~34ms. Open budget is remaining epic work, not a side task. Broad-query follow-up from .2 is not reproduced on this host. Symvision sase-19x.4 entries stay with active epic sase-19x. No --epic-symbol lines for this epic. Commits since epic start outside these stitches do not touch Node Finder code, so no integration edit. Nested plan sase_plan_node_finder_open_floor.md covers only the open-path cut. Do not close this epic until that plan lands and the official open p95 is under 50ms.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.7.3.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.3.land.md) | [sase-19i.7.3](sase-19i.7.3.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19i.7.3.1][1] | parent epic scope | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19i.7.3.1/README.md

<!-- sase:referenced-by:end -->
