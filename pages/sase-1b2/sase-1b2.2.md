# Bead: sase-1b2.2 — FinalizerNodeView projection - decoders, precedence, and selection

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.2` · **Size:** medium
**Created:** 2026-09-27 05:49:31 EDT · **Closed:** 2026-09-27 06:27:45 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

core-run-view-model: in sase-core, add the finalizer run_view module with request/response wires, tolerant capped decoders for every finalizer artifact, the ten source-precedence rules, run disposition and instance statuses, DAG order, selection explanation, declaration timeline, cycles, drift and the attention hint. Also add the project_finalizer_node_view binding.

## Notes

[2026-09-27T10:27:45Z · sase-1b2.2] core-run-view-model done in sase-core checkout: new finalizer::run_view module (wire/decode/precedence/selection/detail/evidence/tests, all files <1500 lines, mod.rs facade only, no macro_rules) with tolerant capped decoders, rules 1-10 precedence, DAG order, selection explanation + unselected with secrecy test, declaration timeline, cycles/reactivations, drift, attention + run_level_trouble; project_finalizer_node_view binding registered in bead_decisions with round-trip + name-presence tests. Verified: 27 run_view + 9 bead_decisions targeted tests green, sase tool run check succeeded in sase-core checkout. No epic-symbol entries. Pin move left to run-view-adapter per plan 3.10.

## Dependencies

- **Blocks:** [sase-1b2.3](sase-1b2.3.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.2/README.md) | [sase-1b2.2](sase-1b2.2.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 1 |
| read-by | [agent:sase-1b2.2][2] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.2/README.md

<!-- sase:referenced-by:end -->
