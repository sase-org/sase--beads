# Bead: sase-yy.8.3 — Reduce event unions and keep bead projections consistent

[Bead Pages](../README.md) / [sase-yy.8](sase-yy.8.md) / sase-yy.8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-yy.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.land.md) · **Assignee:** `sase-yy.8.3` · **Size:** large
**Created:** 2026-09-10 14:27:26 EDT · **Closed:** 2026-09-10 17:51:19 EDT
**Plan:** [202609/artifact\_link\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_landing_repairs.md)

## Description

event_reconciliation: union immutable operations before cross-clone reduction, preserve add-wins and alias semantics, and make bead projection and operation receipts agree with the same reduced truth.

## Notes

[2026-09-10T21:51:19Z · sase-yy.8.3] Implemented event reconciliation: immutable durable events are unioned across eligible stores before Rust reduction, local pending is overlaid once, and bead endpoint projections now install exact Rust-reduced state with per-edge/direction receipts. Verified with sase-core just check, the local binding validator, focused artifact-link event/publisher/bead/reconciliation/acceptance tests, and artifact-create bead attachment tests; this repo's just check remains blocked by live flag bead sase-z0/link_events and unrelated escalated full-suite drift outside this phase.

## Dependencies

- **Depends on:** [sase-yy.8.2](sase-yy.8.2.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-yy.8.4](sase-yy.8.4.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-yy.8.5](sase-yy.8.5.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yy.8.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.8.3.md) | [sase-yy.8.3](sase-yy.8.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`840824c`](https://github.com/sase-org/sase/commit/840824c5bb71a9d78e46ee446625f47cdea0b7d4) | feat(sdd): reconcile artifact link event unions | [sase-yy.8.3](sase-yy.8.3.md) | 2026-09-10 17:53:38 EDT |
| sase-core | [`sase-core@717c36e`](https://github.com/sase-org/sase-core/commit/717c36e7fa0d9ca5e967fb4e058317242570bd50) | feat(beads): project artifact links by edge receipt | [sase-yy.8.3](sase-yy.8.3.md) | 2026-09-10 17:56:21 EDT |
