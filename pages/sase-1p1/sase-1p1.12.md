# Bead: sase-1p1.12 — Identity-free export packs and multi-machine merge

[Bead Pages](../README.md) / [sase-1p1](README.md) / sase-1p1.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.14w](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.14w.md) · **Assignee:** `sase-1p1.12` · **Size:** medium
**Created:** 2026-10-27 15:21:50 EDT · **Closed:** 2026-10-28 04:15:52 EDT
**Plan:** [202610/footprint\_usage\_census.md](https://github.com/sase-org/sase--plans/blob/main/202610/footprint_usage_census.md)

## Previously Closed

> ↺ Closed 2026-10-28T05:44:09Z · done
>
> (none)
>
> Reopened 2026-10-28T06:29:33Z by `sase bead open`

## Description

export_import: add the Rust weekly export projection (buckets, no identity, byte-exact preview) and replace-all import merge, `sase footprint export` and `import`, and merged figures in reports and the card.

## Notes

[2026-10-28T05:44:09Z · sase-1p1.12] Identity-free export/import landed: sase-core sase tool run check green (buckets, replace-all/nonce dedup, merge min(7,local+imported) and observed max, empty-store MAX(imported_day) NULL); Python tests/footprint/test_export.py + binding smoke + report + validate_sase_core_rs (48 passed); catalog has cli:footprint.export/import; preview bytes match file; no leftover --epic-symbol entries.

[2026-10-28T06:38:02Z · sase-1p1.12--1] PROPOSED FOLLOW-UP: KNOWN just check: _RecoveryAssessment private import in src/sase/finalizers/_failed_close_recovery_assess.py (symvision; pre-existing, touched=false; witness 1dc946d3c1a3ec6ed5f0c3cdbaf2e681)

[2026-10-28T07:24:08Z · sase-1p1.12--2] PROPOSED FOLLOW-UP: ratchet sase-core-revision.txt past the sase-core export/import commit after it lands (CI pin; six-hourly ratchet also covers this)

[2026-10-28T08:15:52Z · sase-1p1.12--3] Identity-free export/import verified: Python tests/footprint/test_export.py + binding smoke + validate_sase_core_rs (27 passed); sase-core transfer tests (13 passed: buckets, forbidden IDs, replace-all/nonce, merge min(7,local+imported) and observed max, dry-run); preview bytes match file; catalog has cli:footprint.export/import; no leftover --epic-symbol. just check remains no_new (KNOWN _RecoveryAssessment private import + unrelated workspace/axe flakes; follow-ups already recorded).

[2026-10-28T08:55:12Z · sase-1p1.12--4] PROPOSED FOLLOW-UP: sase-core just check load-flake: tool_run::store::tests::contention::{barrier_orders_exclusive_holder_then_show, retry_after_releasable_lock_does_not_duplicate_run} failed under full check (SQLite busy/WAL timeout), passed in isolation; witness e806578cc8f9fec509172149f2c41b66. Related to sase-18t store-busy flake family.

[2026-10-28T11:57:00Z · sase-1p1.12--9] Catalog match test now generates in a clean subprocess so xdist pollution cannot fail test_checked_in_catalog_matches_generator (was NEW 3652 vs 3653 on just check b01c34b3803ce9e898654eba5873e86b). KNOWN _RecoveryAssessment private import remains a recorded follow-up.

[2026-10-28T12:58:19Z · sase-1p1.12--b] PROPOSED FOLLOW-UP: NEW-classified just check flake tests/test_sudo_ledger_settlement.py::test_sudo_answer_defers_after_long_lock_timeout_and_reclaim_settles_later (assert settled==deferred; touched=false, first_seen before this phase; witness fc0af6fd52c7e17438adc338aeb29e5b)

[2026-10-28T14:47:21Z · sase-1p1.12--d] PROPOSED FOLLOW-UP: FLAKY just check tests/test_agent_artifact_directory_operation_audit.py::test_artifact_directory_operation_sites_are_reviewed (artifact-dir site allowlist drift; touched=false, in reproducible_flake_baseline.txt@3d52c6ce744b; witness e1d42fd027a7e99b9bc1b540b21e6d73)

[2026-10-28T14:47:23Z · sase-1p1.12--d] Identity-free export/import rebased onto origin/master 3d52c6ce74; pin sase-core-revision.txt to 65546fd (export/import bindings). just check e1d42fd027a7e99b9bc1b540b21e6d73: no_new_failures, lint/symvision green, 1 FLAKY artifact-dir audit (baseline, out of scope). No leftover --epic-symbol.

## Dependencies

- **Blocks:** [sase-1p1.13](sase-1p1.13.md) ✓ · ⧖ 2026-10-27
- **Depends on:** [sase-1p1.8](sase-1p1.8.md) ✓ · ⧖ 2026-10-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1p1.12](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1p1.12.md) | [sase-1p1.12](sase-1p1.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@65546fd`](https://github.com/sase-org/sase-core/commit/65546fd244ec43ee023369fdafb5b5edb6197061) | feat(footprint): add identity-free weekly export and replace-all import | [sase-1p1.12](sase-1p1.12.md) | 2026-10-28 09:57:03 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1p1.12--d][1] | Need the phase scope and design file | 2 |
| read-by | [agent:sase-1p1.13][2] | Check what export phase actually delivered | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1p1.12.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1p1.13/README.md

<!-- sase:referenced-by:end -->
