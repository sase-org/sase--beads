# Bead: sase-1hi.10.6 — Telegram submits every option, refreshes stale cards, and settles with true receipts

[Bead Pages](../README.md) / [sase-1hi.10](sase-1hi.10.md) / sase-1hi.10.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1hi.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.land.md) · **Assignee:** `sase-1hi.10.6` · **Size:** large
**Created:** 2026-10-08 05:26:47 EDT · **Closed:** 2026-10-08 11:50:41 EDT
**Plan:** [202610/plan\_decisions\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/plan_decisions_landing_repairs.md)

## Description

telegram: send inputs only for selected options, fix the refresh loop and stale-after-submit, make settle receipts name the true verdict, decider, surface, and defaults, honor the sheet budget, route PDF and receipts through sase.sdd.plan_decisions, and repair the nine failing tests plus the missing coverage.

## Notes

[2026-10-08T15:50:41Z · sase-1hi.10.6--2] Implemented telegram_decisions_repairs: (1) selected-option-only decision submission incl approve+commit identical vectors, empty reject, provisional feedback; (2) refresh-before-revision-check with full prose+keyboard re-render, retained pending action/progress, stale-after-submit and restart recovery; (3) single truthful receipt path via effective_response_input/frozen definitions/stamped recovery with tale/epic verdicts, decider/surface mapping, yes-no/starred defaults, launch-vs-acceptance separation, message-id fallback chain and idempotent delivery; (4) whole-block budget rendering honoring 1800-char sheet order and 4096-char card limit with real expandable blockquotes; (5) pinned keyboard layout with set-state tokens, success styling, frozen/stamped PDF decisions with full callout labelling, removed obsolete flag fixture, fixed split-send markup. Tests: repaired 9 audited failures (5 custom-gate, long-message split, memory, merged-vector, removed-flag) plus new behavioral coverage 1-7 in tests/test_plan_decisions.py, tests/test_custom_gates.py, tests/test_telegram_client.py. Verification: sase tool run check in sase-telegram exit 0 — ruff clean, mypy clean (55 files), 758 passed, 11 PTB timedelta warnings; KNOWN 0 FLAKY 0. sase bead epic-symbols sase-1hi.10.6 empty, no Justfile re-key needed.

## Dependencies

- **Depends on:** [sase-1hi.10.2](sase-1hi.10.2.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1hi.10.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.10.6.md) | [sase-1hi.10.6](sase-1hi.10.6.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1hi.10.6--2][1] | Check phase scope before closing | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1hi.10.6.md

<!-- sase:referenced-by:end -->
