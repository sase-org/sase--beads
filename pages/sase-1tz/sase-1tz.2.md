# Bead: sase-1tz.2 — Publication de-flap, truthful error digests, and TUI stall reduction (items 3-5)

[Bead Pages](../README.md) / [sase-1tz](README.md) / sase-1tz.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1eb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1eb.md) · **Assignee:** `sase-1tz.2` · **Size:** xlarge
**Created:** 2026-11-19 07:09:38 EST
**Plan:** [202611/notification\_log\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/notification_log_audit_fixes.md)

## Description

noise: give agent_publication per-(project, signature) backoff with standing alerts, a bounded incremental drain, and a terminal state for unrestorable prompt archives. Aggregate the error ring and digests by signature with durable true counts and pruning. Cut measured TUI GC pauses and main-thread I/O stalls, with tui_stalls.jsonl as the acceptance metric.

## Dependencies

- **Depends on:** [sase-1tz.1](sase-1tz.1.md) ✓ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.3](sase-1tz.3.md) ◐ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2/README.md) | [sase-1tz.2](sase-1tz.2.md) | 0 |
