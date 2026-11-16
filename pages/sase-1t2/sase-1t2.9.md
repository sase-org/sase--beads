# Bead: sase-1t2.9 — Hijack WAITING, QUEUED, and booting turns that hold a numbered workspace

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.9` · **Size:** medium
**Created:** 2026-11-15 20:00:11 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Description

waiter_branch: allow WAITING/QUEUED/booting turns with a numbered claim (terminate the parked runner, or take the processless branch when it is dead), cancel the turn's own wait marker while waiters of it stay parked, redirect claimless %wait turns to kill-and-edit with a reason, and make Continue relaunch a turn that never reached its provider.

## Dependencies

- **Blocks:** [sase-1t2.13](sase-1t2.13.md) ◐ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.7](sase-1t2.7.md) ◐ · ⧖ 2026-11-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.9/README.md) | [sase-1t2.9](sase-1t2.9.md) | 0 |
