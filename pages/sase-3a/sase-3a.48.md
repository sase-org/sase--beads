# Bead: sase-3a.48 — Remediate pyvision symbol: hook\_status\_line\_to\_wire

[Bead Pages](../README.md) / [sase-3a](README.md) / sase-3a.48

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-13 02:14:21 UTC
**Plan:** [sdd/plans/202605/pyvision\_test\_only\_public\_symbols\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202605/pyvision_test_only_public_symbols_cleanup.md)

## Description

The `hook_status_line_to_wire` symbol is either public when it is referenced but only in the file that it is defined (make the symbol private by adding a `_` prefix--note that usage with `__all__` does not count as a reference), public because it is referenced by external repos (add a `# pyvision: ` pragma that references an external repo), or unused (remove the symbol completely--do not forget to remove test references too). Can you help me analyze this symbol and perform the appropriate action / file change?

IMPORTANT: Make sure to run the `just pyvision` command after you have removed the corresponding `--epic-symbol` line in the Justfile.

## Notes

Privatized hook_status_line_to_wire to _hook_status_line_to_wire, updated callers and tests, removed sase-3a.hook_status_line_to_wire from Justfile and validated with just pyvision sweep.

## Dependencies

- **Depends on:** [sase-3a.45](sase-3a.45.md) ✓
- **Blocks:** [sase-3a.51](sase-3a.51.md) ✓
