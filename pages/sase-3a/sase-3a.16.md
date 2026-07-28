# Bead: sase-3a.16 — Remediate pyvision symbol: StatusFieldUpdateWire

[Bead Pages](../README.md) / [sase-3a](README.md) / sase-3a.16

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-13 02:10:57 UTC · **Closed:** 2026-05-13 07:23:11 UTC
**Plan:** [sdd/plans/202605/pyvision\_test\_only\_public\_symbols\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202605/pyvision_test_only_public_symbols_cleanup.md)

## Description

The `StatusFieldUpdateWire` symbol is either public when it is referenced but only in the file that it is defined (make the symbol private by adding a `_` prefix--note that usage with `__all__` does not count as a reference), public because it is referenced by external repos (add a `# pyvision: ` pragma that references an external repo), or unused (remove the symbol completely--do not forget to remove test references too). Can you help me analyze this symbol and perform the appropriate action / file change?

IMPORTANT: Make sure to run the `just pyvision` command after you have removed the corresponding `--epic-symbol` line in the Justfile.

## Notes

COMMIT: 8f27bff71

## Dependencies

- **Depends on:** [sase-3a.13](sase-3a.13.md) ✓
- **Blocks:** [sase-3a.19](sase-3a.19.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`0d6df3c`](https://github.com/sase-org/sase/commit/0d6df3cec780cac9e38ee73b8d0470a9de9067ec) | ref: make StatusFieldUpdateWire private (sase-3a.16) | [sase-3a.16](sase-3a.16.md) | 2026-05-13 07:23:38 |
