# Bead: sase-3a.77 — Remediate pyvision symbol: resolve\_primary\_workspace\_for\_chat\_install

[Bead Pages](../README.md) / [sase-3a](README.md) / sase-3a.77

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-13 02:17:39 UTC
**Plan:** [sdd/plans/202605/pyvision\_test\_only\_public\_symbols\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202605/pyvision_test_only_public_symbols_cleanup.md)

## Description

The `resolve_primary_workspace_for_chat_install` symbol is either public when it is referenced but only in the file that it is defined (make the symbol private by adding a `_` prefix--note that usage with `__all__` does not count as a reference), public because it is referenced by external repos (add a `# pyvision: ` pragma that references an external repo), or unused (remove the symbol completely--do not forget to remove test references too). Can you help me analyze this symbol and perform the appropriate action / file change?

IMPORTANT: Make sure to run the `just pyvision` command after you have removed the corresponding `--epic-symbol` line in the Justfile.

## Dependencies

- **Depends on:** [sase-3a.74](sase-3a.74.md) ✓
- **Blocks:** [sase-3a.80](sase-3a.80.md) ✓
