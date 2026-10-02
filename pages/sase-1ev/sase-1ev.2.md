# Bead: sase-1ev.2 — App-scoped history service and the public history kit

[Bead Pages](../README.md) / [sase-1ev](README.md) / sase-1ev.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vj.md) · **Assignee:** `sase-1ev.2` · **Size:** medium
**Created:** 2026-10-02 14:43:05 EDT
**Plan:** [202610/memory\_history\_tui.md](https://github.com/sase-org/sase--plans/blob/main/202610/memory_history_tui.md)

## Description

history-service: add one app-scoped AceMemoryHistory over a process-wide shared HistoryService, which the pager provider factory also uses. It provides a stale-while-revalidate timeline memo, content-addressed body and comparison LRUs, single-flight queries, stat-only change tokens, explicit invalidation, and a quiet-time warm-up. Also publish sase.pager.history_kit as the only door ACE uses for history presentation, and migrate the History row onto the service with an honest unavailable state.

## Dependencies

- **Depends on:** [sase-1ev.1](sase-1ev.1.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ev.10](sase-1ev.10.md) ◐ · ⧖ 2026-10-02
- **Blocks:** [sase-1ev.3](sase-1ev.3.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ev.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.2/README.md) | [sase-1ev.2](sase-1ev.2.md) | 0 |
