# Bead: sase-kp.9 — Approved-epic launch runs as a monitor

[Bead Pages](../README.md) / [sase-kp](README.md) / sase-kp.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yy](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yy/README.md) · **Assignee:** `sase-kp.9` · **Size:** medium
**Created:** 2026-08-12 17:30:04 EDT · **Closed:** 2026-08-13 07:02:55 EDT
**Plan:** [202608/sase\_monitor.md](https://github.com/sase-org/sase--plans/blob/main/202608/sase_monitor.md)

## Description

epic-launch: replace the detached epic-launch task with a generic monitor start using `EPIC APPROVED` / `EPIC CREATED`, keeping the host claim and a fallback.

## Notes

[2026-08-13T10:54:09Z · sase-kp.9] PROPOSED FOLLOW-UP: Patch/stitch terminology audit fails on existing changespec tokens — `just check` reports unclassified `changespec` in tests/test_validate_sase_core_rs_tool.py lines 430 and 504 plus tools/validate_sase_core_rs line 606; classify or migrate those references so the whole-repo check can pass.

[2026-08-13T11:02:55Z · sase-kp.9] Implemented approved-epic launch via sase monitor start with EPIC APPROVED -> EPIC CREATED statuses, monitor id reporting, and detached-task fallback. Verified focused approval/monitor tests (107 passed), tests/test_plan_approval_choices.py (5 passed), and just test-scoped escalated full suite (4783 passed, 7 skipped). just check passes fmt/ruff/mypy/pyscripts/test-waits/changelog but is blocked by the pre-existing patch/stitch terminology audit issue recorded as a PROPOSED FOLLOW-UP.

[2026-08-13T11:04:16Z · sase-kp.9] Implemented approved epic launch through sase monitor start; verified focused approval/monitor tests, plan approval choice tests, just test-scoped full-suite escalation, and just check through the known unrelated patch/stitch terminology audit blocker.

## Dependencies

- **Blocks:** [sase-kp.12](sase-kp.12.md) ◐ · ⧖ 2026-08-12
- **Depends on:** [sase-kp.6](sase-kp.6.md) ✓ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-kp.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-kp.9/README.md) | [sase-kp.9](sase-kp.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4479603`](https://github.com/sase-org/sase/commit/44796037a560316e1945b8a5e6d0482d61f15191) | feat(epic-launch): launch approved epics through monitors | [sase-kp.9](sase-kp.9.md) | 2026-08-13 07:05:01 EDT |
