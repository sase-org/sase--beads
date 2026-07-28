# Bead: sase-3a.8 — Remediate pyvision symbol: NotificationStoreStatsWire

[Bead Pages](../README.md) / [sase-3a](README.md) / sase-3a.8

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-13 02:10:08 UTC · **Closed:** 2026-05-13 05:05:13 UTC
**Plan:** [sdd/plans/202605/pyvision\_test\_only\_public\_symbols\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202605/pyvision_test_only_public_symbols_cleanup.md)

## Description

The `NotificationStoreStatsWire` symbol is either public when it is referenced but only in the file that it is defined (make the symbol private by adding a `_` prefix--note that usage with `__all__` does not count as a reference), public because it is referenced by external repos (add a `# pyvision: ` pragma that references an external repo), or unused (remove the symbol completely--do not forget to remove test references too). Can you help me analyze this symbol and perform the appropriate action / file change?

IMPORTANT: Make sure to run the `just pyvision` command after you have removed the corresponding `--epic-symbol` line in the Justfile.

## Notes

COMMIT: ff4dce47a

## Dependencies

- **Blocks:** [sase-3a.11](sase-3a.11.md) ✓
- **Depends on:** [sase-3a.5](sase-3a.5.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`10fef43`](https://github.com/sase-org/sase/commit/10fef435a90b66c07ac465b71759ac314dc09d48) | ref: make NotificationStoreStatsWire private (sase-3a.8) | [sase-3a.8](sase-3a.8.md) | 2026-05-13 05:05:52 |
