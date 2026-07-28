# Bead: sase-3a.3 — Remediate pyvision symbol: CycleError

[Bead Pages](../README.md) / [sase-3a](README.md) / sase-3a.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-13 02:09:34 UTC · **Closed:** 2026-05-13 04:14:12 UTC
**Plan:** [sdd/plans/202605/pyvision\_test\_only\_public\_symbols\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202605/pyvision_test_only_public_symbols_cleanup.md)

## Description

The `CycleError` symbol is either public when it is referenced but only in the file that it is defined (make the symbol private by adding a `_` prefix--note that usage with `__all__` does not count as a reference), public because it is referenced by external repos (add a `# pyvision: ` pragma that references an external repo), or unused (remove the symbol completely--do not forget to remove test references too). Can you help me analyze this symbol and perform the appropriate action / file change?

IMPORTANT: Make sure to run the `just pyvision` command after you have removed the corresponding `--epic-symbol` line in the Justfile.

## Notes

COMMIT: a8fc56441

## Dependencies

- **Blocks:** [sase-3a.6](sase-3a.6.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`e6013f4`](https://github.com/sase-org/sase/commit/e6013f4dda35b15a4ab78fb2d379eac849068782) | ref: make CycleError private (\_CycleError) (sase-3a.3) | [sase-3a.3](sase-3a.3.md) | 2026-05-13 04:14:42 |
