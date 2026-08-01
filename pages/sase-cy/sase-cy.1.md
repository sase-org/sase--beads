# Bead: sase-cy.1 — Canonical snooze state and expiry contract

[Bead Pages](../README.md) / [sase-cy](README.md) / sase-cy.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.qu](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.qu/README.md) · **Assignee:** `sase-cy.1` · **Size:** medium
**Created:** 2026-08-01 10:45:54 UTC · **Closed:** 2026-08-01 11:16:46 UTC
**Plan:** [202608/reliable\_notification\_snoozing.md](https://github.com/sase-org/sase--plans/blob/main/202608/reliable_notification_snoozing.md)

## Description

core-expiry: make the Rust notification store own validated deadlines, atomic active-row expiry, resurface metadata, and next-deadline projection.

## Notes

[2026-08-01T11:16:01Z · sase-cy.1] PROPOSED FOLLOW-UP: Repair strict tale-plan fixtures — tests/test_sdd_file_writes.py::test_write_sdd_files_supports_flat_sidecar_plans_root and ::test_write_sdd_files_rebases_seeded_parent_section still omit newly required title/goal frontmatter, matching the pre-existing failures documented in the epic design.

[2026-08-01T11:16:08Z · sase-cy.1] PROPOSED FOLLOW-UP: Harden suite-gate integration timing under host contention — test_scaled_suite_runs_share_capacity_and_release_after_sigkill timed out after its child printed 100% during concurrent full Rust/Python verification, then passed alone in 7.67s.

[2026-08-01T11:16:46Z · sase-cy.1] Verified canonical UTC deadline validation/normalization, atomic legacy/due expiry to unread resurfaced activity, dismissal/unmute cancellation, next-deadline projection, activity cursor tie-breaking, and concurrent append/two-reader convergence. cargo test --workspace, cargo clippy --workspace --all-targets -- -D warnings, and cargo fmt --check pass in sase-core; 76 focused Python tests pass; main just check passed all format/lint/type/validation gates and its full test run reached 25,005 passes, with the two pre-existing SDD fixture failures noted on the bead and the one contention timeout passing alone.

[2026-08-01T11:17:59Z · sase-cy.1] Verified canonical UTC deadline validation/normalization, atomic legacy/due expiry to unread resurfaced activity, dismissal/unmute cancellation, next-deadline projection, activity cursor tie-breaking, and concurrent append/two-reader convergence. cargo test --workspace, cargo clippy --workspace --all-targets -- -D warnings, and cargo fmt --check pass in sase-core; 76 focused Python tests pass; main just check passed all format/lint/type/validation gates and its full test run reached 25,005 passes, with the two pre-existing SDD fixture failures noted on the bead and the one contention timeout passing alone.

## Dependencies

- **Blocks:** [sase-cy.2](sase-cy.2.md) ◐
- **Blocks:** [sase-cy.3](sase-cy.3.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-cy.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-cy.1/README.md) | [sase-cy.1](sase-cy.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@a856b66`](https://github.com/sase-org/sase-core/commit/a856b6650ddade77956ed06ca706de5d5bde1438) | feat(notifications): define canonical snooze expiry state | [sase-cy.1](sase-cy.1.md) | 2026-08-01 11:18:36 |
| sase | [`09517a0`](https://github.com/sase-org/sase/commit/09517a0fb011f0922e132d34591c2ec380911c6d) | feat(notifications): expose canonical snooze snapshots | [sase-cy.1](sase-cy.1.md) | 2026-08-01 11:19:33 |
