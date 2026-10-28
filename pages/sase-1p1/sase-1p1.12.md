# Bead: sase-1p1.12 — Identity-free export packs and multi-machine merge

[Bead Pages](../README.md) / [sase-1p1](README.md) / sase-1p1.12

**Status:** ○ open · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.14w](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.14w.md) · **Assignee:** `sase-1p1.12` · **Size:** medium
**Created:** 2026-10-27 15:21:50 EDT
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

## Dependencies

- **Blocks:** [sase-1p1.13](sase-1p1.13.md) ◐ · ⧖ 2026-10-27
- **Depends on:** [sase-1p1.8](sase-1p1.8.md) ✓ · ⧖ 2026-10-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1p1.12](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1p1.12.md) | [sase-1p1.12](sase-1p1.12.md) | 0 |
