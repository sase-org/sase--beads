# Bead: sase-3a.17 — Remediate pyvision symbol: StreamedScriptResult

[Bead Pages](../README.md) / [sase-3a](README.md) / sase-3a.17

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-13 02:11:03 UTC · **Closed:** 2026-05-13 06:39:13 UTC
**Plan:** [sdd/plans/202605/pyvision\_test\_only\_public\_symbols\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202605/pyvision_test_only_public_symbols_cleanup.md)

## Description

The `StreamedScriptResult` symbol is either public when it is referenced but only in the file that it is defined (make the symbol private by adding a `_` prefix--note that usage with `__all__` does not count as a reference), public because it is referenced by external repos (add a `# pyvision: ` pragma that references an external repo), or unused (remove the symbol completely--do not forget to remove test references too). Can you help me analyze this symbol and perform the appropriate action / file change?

IMPORTANT: Make sure to run the `just pyvision` command after you have removed the corresponding `--epic-symbol` line in the Justfile.

## Notes

COMMIT: d251b833a

## Dependencies

- **Depends on:** [sase-3a.14](sase-3a.14.md) ✓
- **Blocks:** [sase-3a.20](sase-3a.20.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`34181df`](https://github.com/sase-org/sase/commit/34181dfd7e0ea29d9945a91bbb2730a39009c9d8) | ref: make StreamedScriptResult private (sase-3a.17) | [sase-3a.17](sase-3a.17.md) | 2026-05-13 06:39:34 |
