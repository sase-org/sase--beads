# Bead: sase-8e.1 — Align queue projections with priority-aware admission

[Bead Pages](../README.md) / [sase-8e](README.md) / sase-8e.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-8e.1` · **Size:** small
**Created:** 2026-07-20 19:01:38 UTC
**Plan:** [202607/wait\_priority\_land.md](https://github.com/sase-org/sase--plans/blob/main/202607/wait_priority_land.md)

## Description

'Queue projection integration' section: carry wait priority through presentation-neutral agent models and make existing queue-position calculations follow backend priority ordering.

## Notes

Implemented priority-aware queue projections for integration agent listings and ACE. Added shared wait-priority normalization; propagated wait_priority through AgentWaitInfo, stable agent-list JSON, ACE wire/filesystem enrichment, dedup, and run-now reset; and ordered eligible waiters by normalized priority before timestamp/tie breakers without letting ineligible urgent waiters block eligible waiters. Verification: 75 focused tests passed; full just check passed (20,036 passed, 7 skipped).

## Dependencies

- **Blocks:** [sase-8e.2](sase-8e.2.md) ✓
