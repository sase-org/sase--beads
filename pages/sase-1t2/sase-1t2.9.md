# Bead: sase-1t2.9 — Hijack WAITING, QUEUED, and booting turns that hold a numbered workspace

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.9` · **Size:** medium
**Created:** 2026-11-15 20:00:11 EST · **Closed:** 2026-11-16 04:31:52 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Description

waiter_branch: allow WAITING/QUEUED/booting turns with a numbered claim (terminate the parked runner, or take the processless branch when it is dead), cancel the turn's own wait marker while waiters of it stay parked, redirect claimless %wait turns to kill-and-edit with a reason, and make Continue relaunch a turn that never reached its provider.

## Notes

[2026-11-16T09:31:52Z · sase-1t2.9] Implemented claim-backed hijacks for WAITING, QUEUED, and booting turns, including processless custody, wait-marker cancellation, claimless kill-and-edit redirect, and unstarted Continue prompts. Verified Python/Rust formatting, clean diff checks, and no remaining epic symbols. Primary just fmt stopped at generated docs because sase_core_rs was unavailable; no tests were run.

## Dependencies

- **Blocks:** [sase-1t2.13](sase-1t2.13.md) ◐ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.7](sase-1t2.7.md) ✓ · ⧖ 2026-11-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.9/README.md) | [sase-1t2.9](sase-1t2.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@20b8133`](https://github.com/sase-org/sase-core/commit/20b8133ea3e82a852ccd17a2228820c6a1c97160) | feat(agent-hijack): add pre-provider decisions | [sase-1t2.9](sase-1t2.9.md) | 2026-11-16 04:34:04 EST |
