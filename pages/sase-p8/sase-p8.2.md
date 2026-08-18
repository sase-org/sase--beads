# Bead: sase-p8.2 — Shared pending-handoff marker protocol

[Bead Pages](../README.md) / [sase-p8](README.md) / sase-p8.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05f](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05f.md) · **Assignee:** `sase-p8.2` · **Size:** small
**Created:** 2026-08-17 19:01:00 EDT
**Plan:** [202608/agent\_pipe.md](https://github.com/sase-org/sase--plans/blob/main/202608/agent_pipe.md)

## Description

handoff: give the four marker-writing CLI hand-offs one guard/write/kill helper and one marker registry, and register the pipe marker there.

## Notes

[2026-08-17T23:52:40Z · sase-p8.2] Implemented shared pending-handoff registry + guard/write helper. Named PLAN/QUESTIONS/MONITOR/PIPE markers; PENDING_HANDOFF_MARKERS is derived from them. write_pending_handoff_marker stamps timestamp, writes atomically, fsyncs; handoff_guard refuses missing SASE_AGENT/SASE_ARTIFACTS_DIR and a second marker in one turn. Migrated questions, plan propose, and monitor writers. SIGTERM non-monitor set now includes pipe. Re-keyed stale sase-p1.2 epic-symbols to sase-p1 so just check is not red. Pulse-mtime test now deletes the consumed marker between proposes.

## Dependencies

- **Blocks:** [sase-p8.4](sase-p8.4.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p8.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-p8.2.md) | [sase-p8.2](sase-p8.2.md) | 0 |
