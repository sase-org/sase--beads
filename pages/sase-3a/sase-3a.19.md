# Bead: sase-3a.19 — Remediate pyvision symbol: allocate\_launch\_timestamp\_batch

[Bead Pages](../README.md) / [sase-3a](README.md) / sase-3a.19

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-13 02:11:15 UTC · **Closed:** 2026-05-13 07:55:09 UTC
**Plan:** [sdd/plans/202605/pyvision\_test\_only\_public\_symbols\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202605/pyvision_test_only_public_symbols_cleanup.md)

## Description

The `allocate_launch_timestamp_batch` symbol is either public when it is referenced but only in the file that it is defined (make the symbol private by adding a `_` prefix--note that usage with `__all__` does not count as a reference), public because it is referenced by external repos (add a `# pyvision: ` pragma that references an external repo), or unused (remove the symbol completely--do not forget to remove test references too). Can you help me analyze this symbol and perform the appropriate action / file change?

IMPORTANT: Make sure to run the `just pyvision` command after you have removed the corresponding `--epic-symbol` line in the Justfile.

## Notes

COMMIT: 801166cd1

## Dependencies

- **Depends on:** [sase-3a.16](sase-3a.16.md) ✓
- **Blocks:** [sase-3a.22](sase-3a.22.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`3c3e12c`](https://github.com/sase-org/sase/commit/3c3e12c43455eb9618d5c8bad725f98a848fab92) | ref: make allocate\_launch\_timestamp\_batch private (sase-3a.19) | [sase-3a.19](sase-3a.19.md) | 2026-05-13 07:55:32 |
