# Bead: sase-3a.4 — Remediate pyvision symbol: LegendEpicAssignment

[Bead Pages](../README.md) / [sase-3a](README.md) / sase-3a.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-13 02:09:41 UTC · **Closed:** 2026-05-13 05:00:29 UTC
**Plan:** [sdd/plans/202605/pyvision\_test\_only\_public\_symbols\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202605/pyvision_test_only_public_symbols_cleanup.md)

## Description

The `LegendEpicAssignment` symbol is either public when it is referenced but only in the file that it is defined (make the symbol private by adding a `_` prefix--note that usage with `__all__` does not count as a reference), public because it is referenced by external repos (add a `# pyvision: ` pragma that references an external repo), or unused (remove the symbol completely--do not forget to remove test references too). Can you help me analyze this symbol and perform the appropriate action / file change?

IMPORTANT: Make sure to run the `just pyvision` command after you have removed the corresponding `--epic-symbol` line in the Justfile.

## Notes

COMMIT: d279b54ac

## Dependencies

- **Depends on:** [sase-3a.1](sase-3a.1.md) ✓
- **Blocks:** [sase-3a.7](sase-3a.7.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`bf51d2b`](https://github.com/sase-org/sase/commit/bf51d2b0135ce7c39fb59590171f7454629efa94) | ref: privatize LegendEpicAssignment symbol (sase-3a.4) | [sase-3a.4](sase-3a.4.md) | 2026-05-13 05:00:58 |
