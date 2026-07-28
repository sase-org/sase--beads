# Bead: sase-9k.1 — Bounded deference window for deprioritized waiters

[Bead Pages](../README.md) / [sase-9k](README.md) / sase-9k.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9k.1` · **Size:** medium
**Created:** 2026-07-25 14:38:25 UTC
**Plan:** [sase/repos/plans/202607/wait\_priority.md](https://github.com/sase-org/sase--plans/blob/main/sase/repos/plans/202607/wait_priority.md)

## Description

'Bounded deference window for deprioritized waiters' section: add a priority-scaled, bounded hold-back gate so a below-default-priority waiter does not claim a freshly freed runner slot while a better-priority agent is still finishing its dependency wait, with an early exit when no such agent exists.

## Notes

Implemented bounded priority-scaled runner-slot deference with continuous-eligibility tracking, early exit when no better-priority agent is pending, fail-safe configuration accessors/schema/defaults, log observability, and focused admission/claim/config regressions. Existing AgentMetaWire.wait_priority made a Rust wire change unnecessary.

## Dependencies

- **Blocks:** [sase-9k.2](sase-9k.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-9k.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-9k.1/README.md) | [sase-9k.1](sase-9k.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`43ba5da`](https://github.com/sase-org/sase/commit/43ba5daf72c0d112902fe4b33fbc9bc07e4a86c1) | fix(runner-slots): defer deprioritized admission (sase-9k.1) | [sase-9k.1](sase-9k.1.md) | 2026-07-25 15:06:09 |
