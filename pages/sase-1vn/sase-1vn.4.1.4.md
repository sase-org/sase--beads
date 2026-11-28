# Bead: sase-1vn.4.1.4 — Idempotent land-only launch submission

[Bead Pages](../README.md) / [sase-1vn.4.1](sase-1vn.4.1.md) / sase-1vn.4.1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1vn.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vn.4.md) · **Assignee:** `sase-1vn.4.1.4` · **Size:** medium
**Created:** 2026-11-27 20:17:45 EST
**Plan:** [202611/zombie\_epic\_liveness.md](https://github.com/sase-org/sase--plans/blob/main/202611/zombie_epic_liveness.md)

## Description

recovery-submission: consume published claims through the existing bead-work launch path with deterministic proc identity, a close-token guard, and crash replay tests proving that recovery never relaunches phase workers. Do not enable the periodic job yet.

## Notes

[2026-11-28T05:50:05Z · sase-1vn.4.1.4--1] Verified: 25 new tests pass (test_recovery_submission.py + test_recovery_submission_guard.py) plus 45 neighboring regression tests green; ruff check, ruff format, mypy clean on touched files; sase tool run check exit 0 (run 6fe5681fe54dfeab37894529cf4261d9). Local Justfile has zero 4.1.4 epic-symbol rows (removed 4 upstream-only rows in this diff; added 8 new 4.1.5 rows for scheduler phase). Direct sase bead close refused on upstream-only 4.1.4 rows (expected: cleanup must reach default branch before closing per bead-cli-records.md); host commit via sase_final with bead_action close will land the removal then close.

## Dependencies

- **Depends on:** [sase-1vn.4.1.3](sase-1vn.4.1.3.md) ✓ · ⧖ 2026-11-27
- **Blocks:** [sase-1vn.4.1.5](sase-1vn.4.1.5.md) ◐ · ⧖ 2026-11-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1vn.4.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1vn.4.1.4.md) | [sase-1vn.4.1.4](sase-1vn.4.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a62aafb`](https://github.com/sase-org/sase/commit/a62aafb71899cc6d95dc0ef74ef4ec320bc493ef) | feat(bead): add idempotent land-only recovery launch submission | [sase-1vn.4.1.4](sase-1vn.4.1.4.md) | 2026-11-28 00:51:24 EST |
