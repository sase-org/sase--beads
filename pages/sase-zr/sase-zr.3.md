# Bead: sase-zr.3 — Apply decision and notification changes through ACE's fast path

[Bead Pages](../README.md) / [sase-zr](README.md) / sase-zr.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.0js` · **Assignee:** `sase-zr.3` · **Size:** medium
**Created:** 2026-09-12 05:06:16 EDT · **Closed:** 2026-09-14 11:13:45 EDT
**Plan:** [202609/prompt\_gate\_approval.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_gate_approval.md)

## Description

ace-immediate-projection: Update neutral plan and generic gate submissions in sase to use the shared durable operation and consume its acceptance result. Refresh the exact gate shell, planner, and family plus the cached notification row and indicator promptly, including approvals from Telegram/CLI/mobile. Bypass the broad agent-load cadence only for bounded decision deltas, reuse existing coalescing and pump-free refresh helpers, and protect new state from older snapshots. Keep all disk, subprocess and lock work off Textual's event loop and serial message pump. Verify folded/filtered/off-tab rows, stale overrides, repeated actions, failure recovery and input responsiveness.

## Notes

[2026-09-14T15:13:45Z · sase-zr.3] Implemented durable ACE gate-answer path for neutral plan and generic gate notifications, exact receipt-driven notification/agent refreshes, and inventory/static scanner updates. Verified: targeted notification/inventory/core binding/Justfile tests pass; just check passes; sase bead epic-symbols sase-zr.3 reports no entries.

## Dependencies

- **Depends on:** [sase-zr.2](sase-zr.2.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zr.6](sase-zr.6.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-zr.3/README.md) | [sase-zr.3](sase-zr.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ae6afe9`](https://github.com/sase-org/sase/commit/ae6afe968541d24496496b5c82755f381435afc7) | feat(ace): submit plan gates through durable answers | [sase-zr.3](sase-zr.3.md) | 2026-09-14 14:16:18 EDT |
