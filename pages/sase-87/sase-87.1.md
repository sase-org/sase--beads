# Bead: sase-87.1 — Core upward close cascade and delegated-phase scheduling

[Bead Pages](../README.md) / [sase-87](README.md) / sase-87.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-87.1` · **Size:** medium
**Created:** 2026-07-20 15:01:46 UTC
**Plan:** [202607/bead\_gated\_wait.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_gated_wait.md)

## Description

'Core: upward close cascade and delegated-phase scheduling' section: in sase-core, auto-close a parent phase bead when its last open child (a delegated child epic) closes, exclude phases with an open plan-type child from relaunch waves, and additively expose per-phase blocker bead IDs and the epic's full phase bead ID list on the work-plan payload.

## Notes

COMMIT: f1a23c8

## Dependencies

- **Blocks:** [sase-87.4](sase-87.4.md) ✓
- **Blocks:** [sase-87.6](sase-87.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-87.1--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-87.1.md#member-code) | [sase-87.1](sase-87.1.md) | 0 |
