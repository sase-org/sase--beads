# Bead: sase-lb.1.4 — A monitor handoff never orphans the starter's claim

[Bead Pages](../README.md) / [sase-lb.1](sase-lb.1.md) / sase-lb.1.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.015](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.015.md) · **Assignee:** `sase-lb.1.4` · **Size:** medium
**Created:** 2026-08-14 11:10:19 EDT
**Plan:** [202608/workspace\_claim\_invariant.md](https://github.com/sase-org/sase--plans/blob/main/202608/workspace_claim_invariant.md)

## Description

orphan: make the runner's `monitored` shutdown skip conditional on the claim actually having moved to a live supervisor, so a dead-PID claim is never left behind for the stale-claim reaper.

## Dependencies

- **Depends on:** [sase-lb.1.3](sase-lb.1.3.md) ✓ · ⧖ 2026-08-14
- **Blocks:** [sase-lb.1.7](sase-lb.1.7.md) ◐ · ⧖ 2026-08-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-lb.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-lb.1.4/README.md) | [sase-lb.1.4](sase-lb.1.4.md) | 0 |
