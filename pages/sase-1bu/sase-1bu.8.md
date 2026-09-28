# Bead: sase-1bu.8 — Goals G1 landing fixes: ledger correctness in sase-core and CLI honesty in sase

[Bead Pages](../README.md) / [sase-1bu](README.md) / sase-1bu.8

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1bu.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bu.land.md) · **Assignee:** `sase-1bu.8.land`
**Created:** 2026-09-28 11:36:41 EDT
**Plan:** [202609/goal\_ledger\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/goal_ledger_landing_fixes.md)

## Description

Every goal-ledger defect found while landing G1 (sase-1bu) is fixed and tested before the frozen contract ships. Actions on unknown ids refuse instead of minting phantom goals, criteria keep stable ids, one corrupt file never takes down the whole ledger, and the I/O probe proves what it claims. The `sase goal` CLI does what its help says, and sase's core pin covers the fixes.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bu.8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bu.8.land/README.md) | [sase-1bu.8](sase-1bu.8.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.k.cdx][1] | Verify the current scope and status of the G1 landing-fix child before recommending where to pause | 3 |
| read-by | [agent:research.k.final][2] | Confirm G1 landing-fix scope and status for goals go/no-go consolidation | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.k.cdx/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.k.final/README.md

<!-- sase:referenced-by:end -->
