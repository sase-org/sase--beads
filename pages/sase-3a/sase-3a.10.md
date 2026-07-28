# Bead: sase-3a.10 — Remediate pyvision symbol: ParseErrorWire

[Bead Pages](../README.md) / [sase-3a](README.md) / sase-3a.10

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-13 02:10:21 UTC · **Closed:** 2026-05-13 06:22:10 UTC
**Plan:** [sdd/plans/202605/pyvision\_test\_only\_public\_symbols\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202605/pyvision_test_only_public_symbols_cleanup.md)

## Description

The `ParseErrorWire` symbol is either public when it is referenced but only in the file that it is defined (make the symbol private by adding a `_` prefix--note that usage with `__all__` does not count as a reference), public because it is referenced by external repos (add a `# pyvision: ` pragma that references an external repo), or unused (remove the symbol completely--do not forget to remove test references too). Can you help me analyze this symbol and perform the appropriate action / file change?

IMPORTANT: Make sure to run the `just pyvision` command after you have removed the corresponding `--epic-symbol` line in the Justfile.

## Notes

COMMIT: 3f268128a

## Dependencies

- **Blocks:** [sase-3a.13](sase-3a.13.md) ✓
- **Depends on:** [sase-3a.7](sase-3a.7.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`d349f1c`](https://github.com/sase-org/sase/commit/d349f1c19240c8b22ef52b0387fa60e14467eea3) | ref: add pyvision pragma for ParseErrorWire (sase-3a.10) | [sase-3a.10](sase-3a.10.md) | 2026-05-13 06:23:01 |
