# Bead: sase-1b2.19 — Remove the flag, add goldens, inspect live, and bench

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.19

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.19` · **Size:** medium
**Created:** 2026-09-27 05:49:54 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

final-cutover: bench the j/k and triage loop with the flag off and on, then delete the Off branches and the ace_final_deck registry entry and close its flag bead. Add deterministic goldens for every glance and deck state, re-baseline and inspect the changed subtitle and picker goldens, and inspect live captures.

## Notes

[2026-09-27T10:09:53Z · 0t2] CROSS-EPIC (sase-1b1): if deck views have landed, removing `ace_final_deck` also changes 1b1's goldens: `agents_deck_view_*` and every deck-title golden whose subtitle switcher gains `final`. Re-baseline and inspect them with the rest. The new FINAL goldens show the view badge on Main/Files panels (for example in the Reply/FINAL split) and none on FINAL, and the narrow title tiers golden should confirm FINAL's tab-only rungs. For the bench, the flag-off run already includes 1b1's badge, so a p95 miss there predates FINAL: cite it rather than optimizing FINAL for it. During live inspection, confirm that `P` is unavailable on a focused FINAL panel. The full shared rules are in the NOTES on epic sase-1b2.

## Dependencies

- **Depends on:** [sase-1b2.13](sase-1b2.13.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1b2.18](sase-1b2.18.md) ◐ · ⧖ 2026-09-27
- **Blocks:** [sase-1b2.20](sase-1b2.20.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.19](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.19/README.md) | [sase-1b2.19](sase-1b2.19.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md

<!-- sase:referenced-by:end -->
