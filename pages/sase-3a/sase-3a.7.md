# Bead: sase-3a.7 — Remediate pyvision symbol: NotificationCountsWire

[Bead Pages](../README.md) / [sase-3a](README.md) / sase-3a.7

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-13 02:10:00 UTC · **Closed:** 2026-05-13 05:35:11 UTC
**Plan:** [sdd/plans/202605/pyvision\_test\_only\_public\_symbols\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202605/pyvision_test_only_public_symbols_cleanup.md)

## Description

The `NotificationCountsWire` symbol is either public when it is referenced but only in the file that it is defined (make the symbol private by adding a `_` prefix--note that usage with `__all__` does not count as a reference), public because it is referenced by external repos (add a `# pyvision: ` pragma that references an external repo), or unused (remove the symbol completely--do not forget to remove test references too). Can you help me analyze this symbol and perform the appropriate action / file change?

IMPORTANT: Make sure to run the `just pyvision` command after you have removed the corresponding `--epic-symbol` line in the Justfile.

## Notes

COMMIT: 79ec74a1e

## Dependencies

- **Blocks:** [sase-3a.10](sase-3a.10.md) ✓
- **Depends on:** [sase-3a.4](sase-3a.4.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`0018cb8`](https://github.com/sase-org/sase/commit/0018cb8599352d140e2d1ec1802bfd643c4a0944) | ref: make NotificationCountsWire private (\_NotificationCountsWire) (sase-3a.7) | [sase-3a.7](sase-3a.7.md) | 2026-05-13 05:36:03 |
