# Bead: sase-1q.1 — Phase 1: Fix Pyvision in Chezmoi

[Bead Pages](../README.md) / [sase-1q](README.md) / sase-1q.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-1q.1`
**Created:** 2026-05-01 06:13:25 UTC
**Plan:** [202605/pyvision\_alias\_pragmas.md](https://github.com/sase-org/sase--plans/blob/main/202605/pyvision_alias_pragmas.md)

## Description

Modify /home/bryan/.local/share/chezmoi/home/bin/executable_pyvision to use AST-backed usage collection, scan tracked Python usage-only files outside the target tree, reject test-file pragmas, add bashunit regression tests, run focused tests and chezmoi just check, commit via SASE commit, then run chezmoi apply --force.

## Notes

COMMIT: 96b3cb53

## Dependencies

- **Blocks:** [sase-1q.2](sase-1q.2.md) ✓
