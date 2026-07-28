# Bead: sase-3a.74 — Remediate pyvision symbol: read\_status\_from\_lines\_python

[Bead Pages](../README.md) / [sase-3a](README.md) / sase-3a.74

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-13 02:17:14 UTC
**Plan:** [sdd/plans/202605/pyvision\_test\_only\_public\_symbols\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202605/pyvision_test_only_public_symbols_cleanup.md)

## Description

The `read_status_from_lines_python` symbol is either public when it is referenced but only in the file that it is defined (make the symbol private by adding a `_` prefix--note that usage with `__all__` does not count as a reference), public because it is referenced by external repos (add a `# pyvision: ` pragma that references an external repo), or unused (remove the symbol completely--do not forget to remove test references too). Can you help me analyze this symbol and perform the appropriate action / file change?

IMPORTANT: Make sure to run the `just pyvision` command after you have removed the corresponding `--epic-symbol` line in the Justfile.

## Notes

Made symbol private with underscore and updated parity tests; removed epic-symbol from Justfile.

## Dependencies

- **Depends on:** [sase-3a.71](sase-3a.71.md) ✓
- **Blocks:** [sase-3a.77](sase-3a.77.md) ✓
