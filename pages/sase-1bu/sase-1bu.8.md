# Bead: sase-1bu.8 — Goals G1 landing fixes: ledger correctness in sase-core and CLI honesty in sase

[Bead Pages](../README.md) / [sase-1bu](README.md) / sase-1bu.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1bu.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bu.land.md) · **Assignee:** `sase-1bu.8.land`
**Created:** 2026-09-28 11:36:41 EDT · **Closed:** 2026-09-28 14:21:30 EDT
**Plan:** [202609/goal\_ledger\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/goal_ledger_landing_fixes.md)

## Description

Every goal-ledger defect found while landing G1 (sase-1bu) is fixed and tested before the frozen contract ships. Actions on unknown ids refuse instead of minting phantom goals, criteria keep stable ids, one corrupt file never takes down the whole ledger, and the I/O probe proves what it claims. The `sase goal` CLI does what its help says, and sase's core pin covers the fixes.

## Notes

[2026-09-28T18:21:30Z · sase-1bu.8.land] Verified both closed phases against plan and source: sase-core 32d80d6 covers unknown-id no-write refusals, normalized IDs, criterion IDs/validation, corrupt-event isolation, projection/doctor repair, reducer and wire fixes, and real I/O probe; sase 4feb59611b pins that commit and fixes CLI numbering/status/cross-project IDs, doctor context, locked reconcile and bounded bead-link repush, test isolation, and phantom-goal regressions. All 114 goals plus bead push tests pass with the locally rebuilt core binding; core phase recorded green check b1d6b6c6. Reviewed later commits since the child began; artifact-link integration is covered by reconcile/repush tests, while later TUI/agent changes require no goal integration. Follow-up outcomes: sase-1bu.8.2 #1 bead-candidates duplicates sase-14o (+1); its agent/tab/set:tab gap belongs to active sase-1bc (DISCOVERED ISSUE note). #2 generated goals memory drift was G1-caused, fixed by memory init commit 73eaa9fab0, check now clean, and duplicate task sase-1c7 closed. Check e75e56ccb46d2113790301ac0a974915 passed lint, validation, and 779 scoped tests; its two red nodes are unrelated agent-tabs terminology (recorded on sase-1bc) and known config schema drift. No epic-symbol entries remain.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bu.8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bu.8.land/README.md) | [sase-1bu.8](sase-1bu.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@5365df6`](https://github.com/sase-org/sase--plans/commit/5365df6e1a17869e8db2c750774dcf946c52caad) | docs(goals): mark G1 and landing fix plans done | [sase-1bu.8](sase-1bu.8.md) | 2026-09-28 14:28:07 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.k.cdx][1] | Verify the current scope and status of the G1 landing-fix child before recommending where to pause | 3 |
| read-by | [agent:research.k.final][2] | Confirm G1 landing-fix scope and status for goals go/no-go consolidation | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.k.cdx/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.k.final/README.md

<!-- sase:referenced-by:end -->
