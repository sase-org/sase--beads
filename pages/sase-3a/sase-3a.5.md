# Bead: sase-3a.5 — Remediate pyvision symbol: MultiAgentXPromptDepthError

[Bead Pages](../README.md) / [sase-3a](README.md) / sase-3a.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-13 02:09:47 UTC · **Closed:** 2026-05-13 04:33:06 UTC
**Plan:** [sdd/plans/202605/pyvision\_test\_only\_public\_symbols\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202605/pyvision_test_only_public_symbols_cleanup.md)

## Description

The `MultiAgentXPromptDepthError` symbol is either public when it is referenced but only in the file that it is defined (make the symbol private by adding a `_` prefix--note that usage with `__all__` does not count as a reference), public because it is referenced by external repos (add a `# pyvision: ` pragma that references an external repo), or unused (remove the symbol completely--do not forget to remove test references too). Can you help me analyze this symbol and perform the appropriate action / file change?

IMPORTANT: Make sure to run the `just pyvision` command after you have removed the corresponding `--epic-symbol` line in the Justfile.

## Notes

COMMIT: 8aa3400c2

## Dependencies

- **Depends on:** [sase-3a.2](sase-3a.2.md) ✓
- **Blocks:** [sase-3a.8](sase-3a.8.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`1ea1ed5`](https://github.com/sase-org/sase/commit/1ea1ed585b78105dc4a44c89bc0da641fc61c8f2) | chore: make MultiAgentXPromptDepthError symbol private (sase-3a.5) | [sase-3a.5](sase-3a.5.md) | 2026-05-13 04:33:43 |
