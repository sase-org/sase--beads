# Bead: sase-65.2 — Replace timing-based captures with expected-state waits

[Bead Pages](../README.md) / [sase-65](README.md) / sase-65.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-65.2`
**Created:** 2026-07-15 22:02:50 UTC
**Plan:** [202607/visual\_snapshot\_determinism.md](https://github.com/sase-org/sase--plans/blob/main/202607/visual_snapshot_determinism.md)

## Description

Phase `deterministic-capture` in approved epic plan `sase/repos/plans/202607/visual_snapshot_determinism.md`.

## Notes

Implemented semantic visual-state and SVG-sentinel waits with timeout frame diagnostics; replaced timing-based capture waits across the audited visual offenders; added helper coverage. Verification: five consecutive just test-visual runs each passed 214 with 1 skipped; just test passed 17390 with 7 skipped. just check was run; its only failures were pre-existing mypy and Symvision findings in untouched source files.

## Dependencies

- **Depends on:** [sase-65.1](sase-65.1.md) ✓
- **Blocks:** [sase-65.3](sase-65.3.md) ✓
