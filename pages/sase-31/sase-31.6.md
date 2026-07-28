# Bead: sase-31.6 — Phase 6: Live CI Verification And Residual Failures

[Bead Pages](../README.md) / [sase-31](README.md) / sase-31.6

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-31.6`
**Created:** 2026-05-12 02:02:26 UTC
**Plan:** [202605/github\_actions\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202605/github_actions_recovery.md)

## Description

Implement Phase 6 from sdd/epics/202605/github_actions_recovery.md: verify the latest master workflow set is green and isolate any CI-only residual failures.

## Notes

Final status report: sdd/epics/202605/github_actions_recovery_phase6_report.md. Latest master CI on SHA 6e79f32e is FAIL: visual-test and test (3.14) both fail with 15 ACE PNG snapshot mismatches (~7K pixels/~0.5% per snapshot) — CI-only residual caused by FreeType/cairo glyph rasterization drift between local goldens and the GitHub Actions runner despite Phase 4's bundled Fira Code. Phases 1-3 and 5 are green on this SHA; Phase 4's font-file pinning is necessary but insufficient. Recommended (not filed): regenerate goldens from a CI run, or pin the renderer stack alongside the font. Parent sase-31 remains open.

## Dependencies

- **Depends on:** [sase-31.5](sase-31.5.md) ✓
