# Bead: sase-1ok.4 — Stop plan propose from parenting new epics under an already-closed bead

[Bead Pages](../README.md) / [sase-1ok](README.md) / sase-1ok.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.14p](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.14p.md) · **Assignee:** `sase-1ok.4` · **Size:** small
**Created:** 2026-10-26 18:10:50 EDT · **Closed:** 2026-10-26 19:28:48 EDT
**Plan:** [202610/stranded\_phase\_detection\_and\_wrong\_bead\_guard.md](https://github.com/sase-org/sase--plans/blob/main/202610/stranded_phase_detection_and_wrong_bead_guard.md)

## Description

closed-parent-stamp: skip the automatic parent_bead stamp in sase plan propose when the proposing agent's active bead is already closed, so follow-on campaign epics are top-level instead of growing the ID one segment per batch.

## Notes

[2026-10-26T23:28:48Z · sase-1ok.4] Implemented the closed-parent check, preserved authored parent_bead values, and updated regression tests and bead-work docs. Verified with sase tool run check (exit 0: lint, docs, SASE validation, and scoped tests passed); epic-symbols reports no leftovers.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ok.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ok.4/README.md) | [sase-1ok.4](sase-1ok.4.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ok.4][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ok.4/README.md

<!-- sase:referenced-by:end -->
