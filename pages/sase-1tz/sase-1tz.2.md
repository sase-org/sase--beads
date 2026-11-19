# Bead: sase-1tz.2 — Publication de-flap, truthful error digests, and TUI stall reduction (items 3-5)

[Bead Pages](../README.md) / [sase-1tz](README.md) / sase-1tz.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1eb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1eb.md) · **Assignee:** `sase-1tz.2` · **Size:** xlarge
**Created:** 2026-11-19 07:09:38 EST
**Plan:** [202611/notification\_log\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/notification_log_audit_fixes.md)

## Description

noise: give agent_publication per-(project, signature) backoff with standing alerts, a bounded incremental drain, and a terminal state for unrestorable prompt archives. Aggregate the error ring and digests by signature with durable true counts and pruning. Cut measured TUI GC pauses and main-thread I/O stalls, with tui_stalls.jsonl as the acceptance metric.

## Notes

[2026-11-19T16:46:45Z · sase-1tz.2.1.4] pub_cleanup (sase-1tz.2.1.4): athena 2 Nov-3 `.sase-v2-*` dirs + 27 archive notices; apollo 0 scratch + 3 notices; cleanup cap 15s from athena p50≈1.6/max≈11.8; live sweep gated.

[2026-11-19T16:56:41Z · sase-1tz.2.1.1] error_groups (sase-1tz.2.1.1): ring baseline athena 100 rows/44 publication (Nov14-19), apollo 100 rows/61 publication (Nov17-19); counts durable in error_counts.json after install.

## Dependencies

- **Depends on:** [sase-1tz.1](sase-1tz.1.md) ✓ · ⧖ 2026-11-19
- **Blocks:** [sase-1tz.3](sase-1tz.3.md) ◐ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) | [sase-1tz.2](sase-1tz.2.md) | 0 |
