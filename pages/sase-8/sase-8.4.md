# Bead: sase-8.4 — Phase 4: Split sase\_utils.py into core/ subpackage

[Bead Pages](../README.md) / [sase-8](README.md) / sase-8.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-03-23 02:51:18 UTC · **Closed:** 2026-03-23 03:43:00 UTC
**Plan:** [202603/restructure\_loose\_files.md](https://github.com/sase-org/sase--plans/blob/main/202603/restructure_loose_files.md)

## Description

Break the God module (89 importers, 300 lines) into focused submodules. Highest risk phase.

## Notes

COMMIT: 83a1370

## Dependencies

- **Depends on:** [sase-8.3](sase-8.3.md) ✓
- **Blocks:** [sase-8.5](sase-8.5.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`58f1f64`](https://github.com/sase-org/sase/commit/58f1f640a55aa03e0086d4db4a0dc1be327dcf66) | ref: Split sase\_utils.py into core/ subpackage with time.py, paths.py, shell.py, and changespec.py (sase-8.4) | [sase-8.4](sase-8.4.md) | 2026-03-23 03:43:01 |
