# Bead: sase-65.3 — Cut over to byte-exact comparison and regenerate all goldens

[Bead Pages](../README.md) / [sase-65](README.md) / sase-65.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-65.3`
**Created:** 2026-07-15 22:02:57 UTC
**Plan:** [202607/visual\_snapshot\_determinism.md](https://github.com/sase-org/sase--plans/blob/main/202607/visual_snapshot_determinism.md)

## Description

Phase `exact-goldens` in approved epic plan `sase/repos/plans/202607/visual_snapshot_determinism.md`.

## Notes

Removed the Justfile's injected PNG tolerance defaults so every visual-bearing lane uses byte-exact comparison unless a caller explicitly sets SASE_VISUAL_PNG_* overrides. Added the fingerprint-gated update-visual-snapshots recipe and aligned png_diff documentation. Full canonical-Linux regeneration passed (214 passed, 1 skipped) and produced zero golden diffs because the committed corpus was already byte-identical. Three consecutive non-update just test-visual runs also passed (214 passed, 1 skipped each). Targeted PNG/fingerprint contract tests passed (30 passed). git diff --check passed. just check was run as required; format, keep-sorted, and ruff passed, then it stopped on four unrelated pre-existing mypy errors in _agent_commits.py, _revive_execution.py, and _watcher.py.

## Dependencies

- **Depends on:** [sase-65.2](sase-65.2.md) ✓
- **Blocks:** [sase-65.4](sase-65.4.md) ✓
