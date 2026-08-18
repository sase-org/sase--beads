# Bead: sase-q0.3 — Refuse destructive preparation of an occupied checkout

[Bead Pages](../README.md) / [sase-q0](README.md) / sase-q0.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.06g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.06g.md) · **Assignee:** `sase-q0.3` · **Size:** medium
**Created:** 2026-08-18 13:44:19 EDT
**Plan:** [202608/workspace\_exclusivity.md](https://github.com/sase-org/sase--plans/blob/main/202608/workspace_exclusivity.md)

## Description

guard: write a per-checkout occupant record when an agent takes a workspace and make every destructive preparation path verify exclusive occupancy before it cleans, resets, or checks out, failing the run instead of deleting another agent's work.

## Dependencies

- **Depends on:** [sase-q0.2](sase-q0.2.md) ◐ · ⧖ 2026-08-18
- **Blocks:** [sase-q0.4](sase-q0.4.md) ◐ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-q0.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-q0.3/README.md) | [sase-q0.3](sase-q0.3.md) | 0 |
