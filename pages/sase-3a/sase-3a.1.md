# Bead: sase-3a.1 — Remediate pyvision symbol: ChatInstallConfig

[Bead Pages](../README.md) / [sase-3a](README.md) / sase-3a.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-13 02:09:21 UTC
**Plan:** [sdd/plans/202605/pyvision\_test\_only\_public\_symbols\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/sdd/plans/202605/pyvision_test_only_public_symbols_cleanup.md)

## Description

The `ChatInstallConfig` symbol is either public when it is referenced but only in the file that it is defined (make the symbol private by adding a `_` prefix--note that usage with `__all__` does not count as a reference), public because it is referenced by external repos (add a `# pyvision: ` pragma that references an external repo), or unused (remove the symbol completely--do not forget to remove test references too). Can you help me analyze this symbol and perform the appropriate action / file change?

IMPORTANT: Make sure to run the `just pyvision` command after you have removed the corresponding `--epic-symbol` line in the Justfile.

## Dependencies

- **Blocks:** [sase-3a.4](sase-3a.4.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`4cf3f20`](https://github.com/sase-org/sase/commit/4cf3f20dcaf0e0cbdfba7630de002506da3b98b1) | ref: privatize ChatInstallConfig symbol (sase-3a.1) | [sase-3a.1](sase-3a.1.md) | 2026-05-13 04:09:14 |
