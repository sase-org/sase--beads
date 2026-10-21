# Bead: sase-1nf.8 — Parked endpoints leave the retry loop and the sweep converges

[Bead Pages](../README.md) / [sase-1nf](README.md) / sase-1nf.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.12i](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.12i.md) · **Assignee:** `sase-1nf.8` · **Size:** medium
**Created:** 2026-10-20 13:36:15 EDT · **Closed:** 2026-10-20 19:43:16 EDT
**Plan:** [202610/athena\_apollo\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_apollo_audit_fixes.md)

## Description

links-converge: move parked operations into a replayable parked ledger, make outbox appends idempotent, sweep per document, report projection failures and parked counts in the artifact_link_backfill job status, and expose parked counts in doctor.

## Notes

[2026-10-20T22:56:01Z · sase-1nf.8] PROPOSED FOLLOW-UP: test_tui_app_import_stays_under_startup_budget is 3523 vs cap 3522 on clean merge-base eb96eafd44 with no sase.* growth (tools/tui_import_closure --diff); already noted on sase-1nf.10.1.1

[2026-10-20T22:56:06Z · sase-1nf.8] PROPOSED FOLLOW-UP: test_behavioral_modules_do_not_dispatch_on_ref_prefix leftover util/imported_revision.py — git HEAD startswith("ref:") from sase-1f4 aae7eae667, not pane dispatch; allowlist like _memory_history_tokens.py

[2026-10-20T23:43:16Z · sase-1nf.8] Parked ledger, idempotent append, per-doc sweep, chop check_error, doctor parked counts. Verified mixed drain, requeue, sweep-as-parked, deferred persist does not mark swept, freeze tests keep one outbox row. sase tool run check 5df09255c6a464f92ae1fab618e2858b: 57075 passed; leftover NEW no_ref_prefix (sase-1f4 imported_revision git HEAD ref:), KNOWN import budget 3523 vs 3522, FLAKY agents_sync bounded drain.

## Dependencies

- **Depends on:** [sase-1nf.7](sase-1nf.7.md) ✓ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.8/README.md) | [sase-1nf.8](sase-1nf.8.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.8][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nf.8/README.md

<!-- sase:referenced-by:end -->
