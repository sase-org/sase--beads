# Bead: sase-am.3 — Consolidate lanes without losing coverage

[Bead Pages](../README.md) / [sase-am](README.md) / sase-am.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-am.3` · **Size:** medium
**Created:** 2026-07-28 22:05:58 UTC · **Closed:** 2026-07-28 23:02:35 UTC
**Plan:** [202607/ci\_flakiness\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202607/ci_flakiness_redesign.md)

## Description

lane-consolidation: merge the three perf-floor jobs into one, delete the redundant install-smoke/bead-backend/build/fmt-md-check jobs after folding their unique steps into neighbors, run the visual suite exactly once per run, build docs once per event, and serialize docs deploys.

## Notes

[2026-07-28T23:02:35Z · sase-am.3] Verified actionlint; 19 workflow/lint contract tests; non-visual test-cov (22,942 passed, 80.77% coverage); dedicated visual suite (367 passed, 1 skipped); build-check/twine; core health; and all four consolidated perf artifacts. just check passed formatting and all lint stages, then stopped on pre-existing external provider-skill drift and missing prompt backlinks in July SDD plans.

[2026-07-28T23:03:32Z · sase-am.3] Verified actionlint; 19 workflow/lint contract tests; non-visual test-cov (22,942 passed, 80.77% coverage); dedicated visual suite (367 passed, 1 skipped); build-check/twine; core health; and all four consolidated perf artifacts. just check passed formatting and all lint stages, then stopped on pre-existing external provider-skill drift and missing prompt backlinks in July SDD plans.

## Dependencies

- **Depends on:** [sase-am.2](sase-am.2.md) ✓
- **Blocks:** [sase-am.4](sase-am.4.md) ✓
