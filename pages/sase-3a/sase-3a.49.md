# Bead: sase-3a.49 — Remediate pyvision symbol: is\_idle

[Bead Pages](../README.md) / [sase-3a](README.md) / sase-3a.49

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-13 02:14:27 UTC
**Plan:** [sdd/plans/202605/pyvision\_test\_only\_public\_symbols\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202605/pyvision_test_only_public_symbols_cleanup.md)

## Description

The `is_idle` symbol is either public when it is referenced but only in the file that it is defined (make the symbol private by adding a `_` prefix--note that usage with `__all__` does not count as a reference), public because it is referenced by external repos (add a `# pyvision: ` pragma that references an external repo), or unused (remove the symbol completely--do not forget to remove test references too). Can you help me analyze this symbol and perform the appropriate action / file change?

IMPORTANT: Make sure to run the `just pyvision` command after you have removed the corresponding `--epic-symbol` line in the Justfile.

## Notes

Privatized is_idle to _is_idle, updated caller tests, removed sase-3a.is_idle from Justfile and validated with just pyvision sweep.

## Dependencies

- **Depends on:** [sase-3a.46](sase-3a.46.md) ✓
- **Blocks:** [sase-3a.52](sase-3a.52.md) ✓
