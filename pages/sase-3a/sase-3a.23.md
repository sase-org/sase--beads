# Bead: sase-3a.23 — Remediate pyvision symbol: build\_legend\_work\_plan

[Bead Pages](../README.md) / [sase-3a](README.md) / sase-3a.23

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-13 02:11:39 UTC · **Closed:** 2026-05-13 07:32:11 UTC
**Plan:** [sdd/plans/202605/pyvision\_test\_only\_public\_symbols\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202605/pyvision_test_only_public_symbols_cleanup.md)

## Description

The `build_legend_work_plan` symbol is either public when it is referenced but only in the file that it is defined (make the symbol private by adding a `_` prefix--note that usage with `__all__` does not count as a reference), public because it is referenced by external repos (add a `# pyvision: ` pragma that references an external repo), or unused (remove the symbol completely--do not forget to remove test references too). Can you help me analyze this symbol and perform the appropriate action / file change?

IMPORTANT: Make sure to run the `just pyvision` command after you have removed the corresponding `--epic-symbol` line in the Justfile.

## Notes

COMMIT: 735d302bf

## Dependencies

- **Depends on:** [sase-3a.20](sase-3a.20.md) ✓
- **Blocks:** [sase-3a.26](sase-3a.26.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`76a1ca7`](https://github.com/sase-org/sase/commit/76a1ca786cea858fac54a435389922807e003a67) | ref: make build\_legend\_work\_plan private (sase-3a.23) | [sase-3a.23](sase-3a.23.md) | 2026-05-13 07:32:35 |
