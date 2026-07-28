# Bead: sase-6c.4 — Make periodic update checks revalidate-only between full recomputes

[Bead Pages](../README.md) / [sase-6c](README.md) / sase-6c.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-6c.4`
**Created:** 2026-07-16 15:13:31 UTC
**Plan:** [202607/tui\_pump\_stalls\_and\_startup.md](https://github.com/sase-org/sase--plans/blob/main/202607/tui_pump_stalls_and_startup.md)

## Description

Phase `updates` in approved epic plan `sase/repos/plans/202607/tui_pump_stalls_and_startup.md`.

## Notes

Implemented revalidate-only cached update checks, a configurable 60-minute periodic network recompute cadence, schema/default/docs updates, and regression coverage. Verified with focused tests (117 passed) and full just check.

## Dependencies

- **Blocks:** [sase-6c.5](sase-6c.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-6c.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-6c.4/README.md) | [sase-6c.4](sase-6c.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`578dad2`](https://github.com/sase-org/sase/commit/578dad292b6d603478179eeb8eed070ffe9364ea) | perf(ace): avoid redundant periodic update recomputes (sase-6c.4) | [sase-6c.4](sase-6c.4.md) | 2026-07-16 15:27:55 |
