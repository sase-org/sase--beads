# Bead: sase-5t.2 — Phase 2 — Port the regression suite to pytest + coverage

[Bead Pages](../README.md) / [sase-5t](README.md) / sase-5t.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5t.2`
**Created:** 2026-07-12 21:44:01 UTC
**Plan:** [202607/symvision\_extraction\_1.md](https://github.com/sase-org/sase--plans/blob/main/202607/symvision_extraction_1.md)

## Description

Work in ~/projects/github/bbugyi200/symvision/. Port all 24 chezmoi bash regression tests to pytest, add focused unit coverage, enforce the highest honest coverage threshold (target at least 90%), and verify just check.

## Notes

Ported all 24 chezmoi bash regressions to pytest with shared temporary git/external-repo fixtures; added focused CLI, scanner, pragma, entry-point, external ordering/cache, and fake BD_COMMAND coverage; enforced fail_under=94; just check passes with 67 tests and 94.27% coverage.

## Dependencies

- **Depends on:** [sase-5t.1](sase-5t.1.md) ✓
- **Blocks:** [sase-5t.3](sase-5t.3.md) ✓
