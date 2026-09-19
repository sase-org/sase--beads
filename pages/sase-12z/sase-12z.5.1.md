# Bead: sase-12z.5.1 — Require screenshot goldens in finalizer commits

[Bead Pages](../README.md) / [sase-12z.5](sase-12z.5.md) / sase-12z.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-12z.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-12z.land.md) · **Assignee:** `sase-12z.5.1` · **Size:** small
**Created:** 2026-09-18 20:31:31 EDT · **Closed:** 2026-09-18 21:17:21 EDT
**Plan:** [202609/finish\_screenshot\_maintenance.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_screenshot_maintenance.md)

## Description

finalizer-guidance: teach the canonical finalizer skill to retain every dirty screenshot golden and add the required trailer for unrelated updates, with source and rendered-skill regressions.

## Notes

[2026-09-19T01:16:33Z · sase-12z.5.1] PROPOSED FOLLOW-UP: full-suite transient failures during finalizer-guidance verification — just check escalated to the full non-visual suite and failed tests/fakey/test_monitor_capacity_e2e.py::test_weight_two_land_family_retains_one_claim_through_real_dispatch_and_delayed_child_bootstrap plus tests/test_ace_testing.py::test_ace_page_group_reports_reset_hook_leaks; both passed immediately in focused rerun (2 passed in 70.62s). The monitor-capacity node appears to match existing ready flake task sase-12f; no obvious node-specific task matched the reset-hook node.

[2026-09-19T01:17:21Z · sase-12z.5.1] Updated src/sase/xprompts/skills/sase_final.md to require committing every dirty ACE/pager screenshot golden and documenting unrelated ones with UNRELATED_SCREENSHOT_UPDATES=<reason>; pinned the source and packaged-skill assertions. Verified with sase skill init --diff, focused finalizer skill tests (2 passed), just fix, and just check through all lint plus full non-visual suite; just check failed only on two unrelated full-lane tests that both passed focused rerun (2 passed in 70.62s), recorded as a PROPOSED FOLLOW-UP note. epic-symbols reported no entries.

## Dependencies

- **Blocks:** [sase-12z.5.2](sase-12z.5.2.md) ◐ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12z.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-12z.5.1/README.md) | [sase-12z.5.1](sase-12z.5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3538713`](https://github.com/sase-org/sase/commit/3538713c0d285883a67abb415c07aa00a02ab5a7) | docs(finalizer): require screenshot golden commits | [sase-12z.5.1](sase-12z.5.1.md) | 2026-09-18 21:19:00 EDT |
