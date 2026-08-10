# Bead: sase-j7.2 — Build a global-state leak detector and inventory every leak in the suite

[Bead Pages](../README.md) / [sase-j7](README.md) / sase-j7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-j0.w1.f0](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j0.w1.f0/README.md) · **Assignee:** `sase-j7.2` · **Size:** medium
**Created:** 2026-08-10 15:44:38 EDT · **Closed:** 2026-08-10 17:22:41 EDT
**Plan:** [202608/fix\_sase\_ct\_flake\_class.md](https://github.com/sase-org/sase--plans/blob/main/202608/fix_sase_ct_flake_class.md)

## Description

leak-detector - build an opt-in pytest plugin that snapshots process-global state around every test, distinguishes cache warming from poisoning, and delivers a full-suite inventory artifact of every leak. Reports only; blocks nothing.

## Notes

[2026-08-10T21:22:08Z · sase-j7.2] PROPOSED FOLLOW-UP: make the leak-detector flag available to no-path pytest invocations — the option is registered from tests/conftest.py, so tools/run_pytest fast --sase-detect-global-leaks needs an explicit tests path unless a safely importable early plugin path is added.

[2026-08-10T21:22:41Z · sase-j7.2] Implemented reporting-only --sase-detect-global-leaks pytest detector with xdist aggregation and warm/poison classification; calibration on tests/test_removed_hg_workspace_workflow.py reported the known _VCS_TAG_PATTERN leak; full inventory via tools/run_pytest fast tests passed 28535/10 skipped and wrote file:explicit:ef5ff8dd23bb954daa8c0c7d (4934 poisoning changes across 2118 tests, 36331 warming filtered); just check passed and escalated to the full suite.

[2026-08-10T21:24:05Z · sase-j7.2] Implemented opt-in pytest global-state leak detector; calibration caught _VCS_TAG_PATTERN; full inventory passed (28535 passed, 10 skipped); just check passed.

## References

- file:explicit:ef5ff8dd23bb954daa8c0c7d

## Dependencies

- **Blocks:** [sase-j7.4](sase-j7.4.md) ◐ · ⧖ 2026-08-10
- **Blocks:** [sase-j7.5](sase-j7.5.md) ◐ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-j7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j7.2/README.md) | [sase-j7.2](sase-j7.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6f4a032`](https://github.com/sase-org/sase/commit/6f4a032cd4ae8ffccd3d9707af2b8537d967b6fc) | test: add opt-in global state leak detector | [sase-j7.2](sase-j7.2.md) | 2026-08-10 17:25:21 EDT |
