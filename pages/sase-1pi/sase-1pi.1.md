# Bead: sase-1pi.1 — sase-core master CI passes on macOS, and a core containing the fix publishes

[Bead Pages](../README.md) / [sase-1pi](README.md) / sase-1pi.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.15m](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.15m.md) · **Assignee:** `sase-1pi.1` · **Size:** medium
**Created:** 2026-10-28 20:07:12 EDT
**Plan:** [202610/unblock\_e2\_core\_release\_flow.md](https://github.com/sase-org/sase--plans/blob/main/202610/unblock_e2_core_release_flow.md)

## Description

macos-core: find why wal_mode_probe_consumes_conversion_budget spends 750 ms to 1.2 s of a 250 ms budget on macos-latest. Fix the product if it overshoots its wall-clock budget, or fix the oracle if the overshoot is outside the budget's control, without loosening the bound. Prove that master CI is green on both OSes and that a merge-capable cut publishes a complete core after the fix.

## Notes

[2026-10-29T00:46:11Z · sase-1pi.1] LOCAL FIX CHECKPOINT (2026-10-29 UTC): GitHub CI run 40726794062 reproduced the existing macOS failure at 961.12475ms for a 250ms budget; Ubuntu passed. The Mac host was unreachable. Replaced SQLite nominal busy_timeout waits with a per-connection busy handler using the operation’s absolute Instant deadline for WAL setup and store reads/writes. Added a deterministic simulated scheduler-oversleep test and routed wal_mode_probe_consumes_conversion_budget through with_write_store. just fmt passed. sase tool run check ff5b0cd52a33355cb6323e2456608053 passed: 5549 core tests, 405 gateway tests, 360 macro-LSP tests, and all remaining suites; the two affected tests passed. This is local-only evidence; the change still needs the host commit, green master ci.yml on both OSes, and the next scheduled release-plz cut to publish a complete core. Follow core_cut=wait; do not dispatch a cut.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pi.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pi.1/README.md) | [sase-1pi.1](sase-1pi.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@0fd85e4`](https://github.com/sase-org/sase-core/commit/0fd85e4ab6e61ab0aec9be6b85cdb0026e71816c) | fix(tool-run): enforce SQLite wall-clock busy deadlines | [sase-1pi.1](sase-1pi.1.md) | 2026-10-28 20:58:20 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pi.1][1] | Confirm local fix checkpoint and current phase state before finalization | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pi.1/README.md

<!-- sase:referenced-by:end -->
