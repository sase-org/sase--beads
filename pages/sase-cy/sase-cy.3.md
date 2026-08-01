# Bead: sase-cy.3 — Cross-surface resurface ordering and delivery

[Bead Pages](../README.md) / [sase-cy](README.md) / sase-cy.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.qu](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.qu/README.md) · **Assignee:** `sase-cy.3` · **Size:** medium
**Created:** 2026-08-01 10:46:04 UTC · **Closed:** 2026-08-01 11:52:19 UTC
**Plan:** [202608/reliable\_notification\_snoozing.md](https://github.com/sase-org/sase--plans/blob/main/202608/reliable_notification_snoozing.md)

## Description

downstream-resurface: adopt current-state reads and resurface activity cursors in CLI, mobile gateway, and Telegram projections so old snoozed rows become new visible activity.

## Notes

[2026-08-01T11:51:42Z · sase-cy.3] PROPOSED FOLLOW-UP: Repair stale SDD write fixtures — test_write_sdd_files_supports_flat_sidecar_plans_root and test_write_sdd_files_rebases_seeded_parent_section still omit newly required tale-plan title and goal fields; both fail in the full check and in isolation as documented by the epic baseline.

[2026-08-01T11:52:19Z · sase-cy.3] Implemented current-state CLI/Python mobile reads, activity-at plus ID ordering/cursors, Rust gateway resurface wire and post-lock expiry events, and Telegram versioned cursor migration with oldest-first stop-on-failure delivery. Verified focused main notification suites (42 passed before final added cases; all task cases passed in the full run), Telegram just check (512 passed), Rust cargo fmt/clippy -D warnings/cargo test --workspace, gateway contract snapshots, and git diff --check in all three repos. Main just check reached 25,009 passed with only the two pre-existing SDD fixture failures documented in the epic; their isolated rerun still fails for missing title/goal, while the transient concurrency failure passed in isolation.

## Dependencies

- **Depends on:** [sase-cy.1](sase-cy.1.md) ✓
- **Blocks:** [sase-cy.4](sase-cy.4.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-cy.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-cy.3/README.md) | [sase-cy.3](sase-cy.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`459ef97`](https://github.com/sase-org/sase/commit/459ef9786dd1ff5ef39ea4eb6f556ccf8db3ceae) | feat(notifications): order projections by resurface activity | [sase-cy.3](sase-cy.3.md) | 2026-08-01 12:01:55 |
