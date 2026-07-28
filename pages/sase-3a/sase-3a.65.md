# Bead: sase-3a.65 — Remediate pyvision symbol: persist\_bulk\_dismiss\_transaction

[Bead Pages](../README.md) / [sase-3a](README.md) / sase-3a.65

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-13 02:16:13 UTC
**Plan:** [sdd/plans/202605/pyvision\_test\_only\_public\_symbols\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202605/pyvision_test_only_public_symbols_cleanup.md)

## Description

The `persist_bulk_dismiss_transaction` symbol is either public when it is referenced but only in the file that it is defined (make the symbol private by adding a `_` prefix--note that usage with `__all__` does not count as a reference), public because it is referenced by external repos (add a `# pyvision: ` pragma that references an external repo), or unused (remove the symbol completely--do not forget to remove test references too). Can you help me analyze this symbol and perform the appropriate action / file change?

IMPORTANT: Make sure to run the `just pyvision` command after you have removed the corresponding `--epic-symbol` line in the Justfile.

## Notes

Private symbol migration completed: renamed _persist_bulk_dismiss_transaction and updated call sites/tests; removed epic-symbol from Justfile.

## Dependencies

- **Depends on:** [sase-3a.62](sase-3a.62.md) ✓
- **Blocks:** [sase-3a.68](sase-3a.68.md) ✓
