# Bead: sase-19i.7.3.3 — Cut the Node Finder open path under the 50 ms budget

[Bead Pages](../README.md) / [sase-19i.7.3](sase-19i.7.3.md) / sase-19i.7.3.3

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19i.7.3.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.3.land.md) · **Assignee:** `sase-19i.7.3.3.land`
**Created:** 2026-09-26 12:33:53 EDT
**Plan:** [202609/node\_finder\_open\_floor.md](https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_open_floor.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/node_finder_open_floor.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/node_finder_open_floor.md

<!-- sase:links:end -->

## Description

The 2,000-node Node Finder open benchmark stays under 50 ms p95, with the other approved budgets still green and navigation behavior unchanged.

## Notes

[2026-09-26T19:45:35Z · sase-1ao.3.land] DISCOVERED ISSUE: just check on sase master (tool run a4c074f6f392e1476eccdbc56bb03530) stops at lint (symvision) because Justfile still passes --epic-symbol 'sase-19i.7.3.3.2(describe_node_finder_row_from_facts)' and that phase is closed. describe_node_finder_row_from_facts is only called from tests/ace/tui/test_node_finder_snapshot.py. Phase note #4 says the epic-symbol was resolved. This blocks every later sase just check until the whitelist entry is removed and the symbol is wired, privatized, pragma'd, or deleted. Found while landing sase-1ao.3; not caused by the model-shortcut pin.

[2026-09-26T19:48:58Z · sase-19i.7.3.3.land] LAND REVIEW, pending child plan: inspected both closed phase notes and commits f079c0af5d/64b15bdf52. Their facet batching, snapshot fast paths, and focused differential tests are present, but the approved benchmark still fails on HEAD f583cd5097: open p50 77.47ms/p95 102.19ms (budget <50); broad refilter p50 12.29ms/p95 17.81ms (budget <16). Narrow p95 1.03ms and highlight p95 0.57ms pass. Both failures are remaining epic work and will be planned in a nested child. Follow-up triage: phase .1 note #1 and phase .2 note #1 are the open failure; phase .2 note #2 is the broad failure. Phase .1 note #3 old unused-public list is no longer reported by just symvision; current private-import error is a different regression already recorded on active sase-1ab note #1 and independently corroborated there. Phase .2 note #3 card_blocks flag issue was retired by closed sase-1ad; the five Node Finder PNG failures are already recorded on active ancestor sase-19i note #5 and remain for its land agent. Phase .2 check baseline is currently blocked by the sase-1ab private-import Symvision error. No distinct unowned task follow-up remains. Since the first epic stitch, later gate-turn commit d5fc75864f updated Agent role naming and Node Finder rendering imports; current finder code consumes those Agent properties, and the perf child must verify their exact semantics. Other later commits do not create a new Node Finder caller. No --epic-symbol entries remain for this epic.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19i.7.3.3.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.3.3.land.md) | [sase-19i.7.3.3](sase-19i.7.3.3.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ao.3.land][1] | Need whether the node-finder epic is still open so the stale symbol can be recorded there | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ao.3.land/README.md

<!-- sase:referenced-by:end -->
