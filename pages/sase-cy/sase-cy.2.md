# Bead: sase-cy.2 — Deadline-driven ACE reminders

[Bead Pages](../README.md) / [sase-cy](README.md) / sase-cy.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.qu](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.qu/README.md) · **Assignee:** `sase-cy.2` · **Size:** medium
**Created:** 2026-08-01 10:46:00 UTC · **Closed:** 2026-08-01 12:20:25 UTC
**Plan:** [202608/reliable\_notification\_snoozing.md](https://github.com/sase-org/sase--plans/blob/main/202608/reliable_notification_snoozing.md)

## Description

ace-deadlines: add a pump-free nearest-deadline coordinator that remains reliable across refresh settings, restarts, suspend, clock changes, and notification mutations.

## Notes

[2026-08-01T11:51:24Z · sase-cy.2] PROPOSED FOLLOW-UP: Repair stale SDD writer fixtures — test_write_sdd_files_supports_flat_sidecar_plans_root and test_write_sdd_files_rebases_seeded_parent_section still omit newly required tale title/goal fields and fail repository-wide just check, matching the epic baseline audit.

[2026-08-01T11:51:50Z · sase-cy.2] PROPOSED FOLLOW-UP: Eliminate pytest opencode temp leak — repository-wide just check still leaves /var/tmp/sase-*/opencode outside the managed pytest temp root, matching the epic baseline audit.

[2026-08-01T12:19:58Z · sase-cy.2] PROPOSED FOLLOW-UP: Stabilize suite-gate capacity integration under concurrent repository checks — test_scaled_suite_runs_share_capacity_and_release_after_sigkill failed only in the four-worker contended just check but passed alone in 14.02s.

[2026-08-01T12:20:25Z · sase-cy.2] Verified pump-free nearest-deadline scheduling, startup/watcher/mutation reconciliation, one-second wall-clock rechecks, overlap coalescing, teardown, exact UTC duration arithmetic across DST, cross-process resurfacing alerts without full Agents reloads, and tracked stale-safe single-row snooze writes. Focused matrix: 105 passed. Final just check passed every static gate and 25,016 tests (7 skipped); its two known SDD fixture failures are recorded as proposed follow-up, and the contended suite-gate failure passed alone (1 passed in 14.02s) and is also recorded.

[2026-08-01T12:22:00Z · sase-cy.2] Verified pump-free nearest-deadline scheduling, startup/watcher/mutation reconciliation, one-second wall-clock rechecks, overlap coalescing, teardown, exact UTC duration arithmetic across DST, cross-process resurfacing alerts without full Agents reloads, and tracked stale-safe single-row snooze writes. Focused matrix: 105 passed. Final just check passed every static gate and 25,016 tests (7 skipped); its two known SDD fixture failures are recorded as proposed follow-up, and the contended suite-gate failure passed alone (1 passed in 14.02s) and is also recorded.

## Dependencies

- **Depends on:** [sase-cy.1](sase-cy.1.md) ✓
- **Blocks:** [sase-cy.4](sase-cy.4.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-cy.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-cy.2/README.md) | [sase-cy.2](sase-cy.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`38c57e1`](https://github.com/sase-org/sase/commit/38c57e178101114294aee51a8563e23ed9dbceec) | feat(ace): schedule snooze reminders by deadline | [sase-cy.2](sase-cy.2.md) | 2026-08-01 12:22:52 |
