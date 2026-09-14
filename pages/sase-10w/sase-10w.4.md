# Bead: sase-10w.4 — Re-derive the scoped lane's serial-budget crossover from current evidence

[Bead Pages](../README.md) / [sase-10w](README.md) / sase-10w.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0kh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0kh.md) · **Assignee:** `sase-10w.4` · **Size:** small
**Created:** 2026-09-14 09:06:48 EDT · **Closed:** 2026-09-14 09:42:58 EDT
**Plan:** [202609/green\_ci\_fast\_lane\_v0\_17\_2.md](https://github.com/sase-org/sase--plans/blob/main/202609/green_ci_fast_lane_v0_17_2.md)

## Description

budget-recalibration: measure the governed full lane's current wall clock at the worker widths agents actually get, and update or deliberately confirm the 232 s crossover constant with recorded provenance.

## Notes

[2026-09-14T13:42:58Z · sase-10w.4] Recalibrated FULL_LANE_WALL_SECONDS to 444.0 from five recent athena full fast lane records at 14 workers (435.2-493.5s, median 443.5s), updated docs/tests, and added public monitor store wrappers needed by the check fixture. Verified: targeted selection-health/report tests passed (72 passed); symvision passed; just check passed all lint/validation stages and escalated to full lane, then failed only on known sibling-phase red test tests/test_justfile_lint.py::test_rust_dev_install_disables_cargo_incremental_cache.

## Dependencies

- **Blocks:** [sase-10w.5](sase-10w.5.md) ◐ · ⧖ 2026-09-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-10w.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-10w.4/README.md) | [sase-10w.4](sase-10w.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`526df13`](https://github.com/sase-org/sase/commit/526df13e48b81e8128b37552e76233e362d75775) | fix(scope): recalibrate scoped lane budget | [sase-10w.4](sase-10w.4.md) | 2026-09-14 10:14:34 EDT |
