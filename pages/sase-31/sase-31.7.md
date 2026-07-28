# Bead: sase-31.7 — Phase 7: Eliminate ACE PNG Snapshot Render Drift

[Bead Pages](../README.md) / [sase-31](README.md) / sase-31.7

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com`
**Created:** 2026-05-12 04:24:12 UTC · **Closed:** 2026-05-12 04:34:04 UTC
**Plan:** [202605/github\_actions\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202605/github_actions_recovery.md)

## Description

Adopt CI-rendered PNGs as new goldens and loosen png_diff.py defaults to absorb sub-pixel rasterization drift across hosts. Implements Option 1 from sdd/epics/202605/github_actions_recovery_phase6_report.md. Plan: sdd/tales/202605/sase_31_close_ace_png_drift.md

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`d102fa8`](https://github.com/sase-org/sase/commit/d102fa8d381379429d6d7912138b622cf6f126bb) | fix(ace/visual): adopt CI-rendered PNG goldens and absorb sub-pixel render drift (Phase 7 of sase-31) (sase-31.7) | [sase-31.7](sase-31.7.md) | 2026-05-12 04:34:20 |
