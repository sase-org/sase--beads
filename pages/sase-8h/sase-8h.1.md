# Bead: sase-8h.1 — Re-anchorable date bounds and end-of-day until

[Bead Pages](../README.md) / [sase-8h](README.md) / sase-8h.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-8h.1` · **Size:** medium
**Created:** 2026-07-21 14:14:41 UTC
**Plan:** [202607/commits\_filter\_correctness.md](https://github.com/sase-org/sase--plans/blob/main/202607/commits_filter_correctness.md)

## Description

'Phase 1: Re-anchorable date bounds and end-of-day until' section: rework sase/vcs_log/dates.py and the commit filter query model so day-granular until: values resolve to end-of-day, and relative bounds (24h/7d/...) are stored as re-anchorable bound specs whose epoch is resolved with an explicit now at use time, with text-normalized value equality.

## Notes

COMMIT: 5a0077672

## Dependencies

- **Blocks:** [sase-8h.2](sase-8h.2.md) ✓
- **Blocks:** [sase-8h.3](sase-8h.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-8h.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-8h.1/README.md) | [sase-8h.1](sase-8h.1.md) | 1 |
| [bbugyi200.athena.sase-8h.1--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-8h.1.md#member-code) | [sase-8h.1](sase-8h.1.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`08f91b4`](https://github.com/sase-org/sase/commit/08f91b43df3ccac5f40b2d7a334973ed7ddd8e85) | fix(vcs): re-anchor date filter bounds (sase-8h.1) | [sase-8h.1](sase-8h.1.md) | 2026-07-21 14:38:56 |
