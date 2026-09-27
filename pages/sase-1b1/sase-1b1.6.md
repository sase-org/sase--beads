# Bead: sase-1b1.6 — View goldens, live inspection, and forced-spread benchmarks

[Bead Pages](../README.md) / [sase-1b1](README.md) / sase-1b1.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sx](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sx.md) · **Assignee:** `sase-1b1.6` · **Size:** medium
**Created:** 2026-09-27 05:45:23 EDT
**Plan:** [202609/deck\_views.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_views.md)

## Description

verify: add new deck-view PNG scenarios and inspect live screenshots at wide and narrow widths. Benchmark P transitions on the 5,000-line Reply, a pathological Reply, and a forced Files spread against stated budgets. Mitigate only by measured rules, then run the acceptance checklist.

## Notes

[2026-09-27T10:08:47Z · 0t2] CROSS-EPIC (sase-1b2): generate the `agents_deck_view_*` goldens with `ace_final_deck` at its default (off) so FINAL never appears; sase-1b2.19 re-baselines them when it removes that flag. If sase-1b2.11 (the CardDocumentView extraction) landed after 1b1.2, re-run `test_deck_view_main_pilot.py`, the Files view pilots and the bench to confirm the forced-policy and anchor-restore paths survived the refactor. Any breakage there is 1b1 behavior, so fix it in this phase. If FINAL is already registered (sase-1b2.14 closed), add a pilot assertion with the flag on that a FINAL panel shows no badge and `P` is unavailable there. The full shared rules are in the NOTES on epic sase-1b1.

## Dependencies

- **Depends on:** [sase-1b1.5](sase-1b1.5.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b1.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.6.md) | [sase-1b1.6](sase-1b1.6.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c.r0][1] | Review sase-1b1 phase progress and notes for value-added research report | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c.r0/README.md

<!-- sase:referenced-by:end -->
