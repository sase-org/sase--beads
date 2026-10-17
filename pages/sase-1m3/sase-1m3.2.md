# Bead: sase-1m3.2 — Per-project linked-repo resolution and declared-by provenance

[Bead Pages](../README.md) / [sase-1m3](README.md) / sase-1m3.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.1s.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.1s.linker.w0.md) · **Assignee:** `sase-1m3.2` · **Size:** medium
**Created:** 2026-10-16 22:05:21 EDT
**Plan:** [202610/sase\_stats\_project.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_stats_project.md)

## Description

inventory: fix sase-1lk so another project's linked repos never absorb the cwd project's entries, and record whether each linked repo was declared by the project or by user-wide config.

## Notes

[2026-10-17T02:26:26Z · sase-1m3.2] PROPOSED FOLLOW-UP: Reuse RepoRecord.declared_by in sase-1l2 — the stats loader can classify project-declared versus user-linked repos without name heuristics.

[2026-10-17T02:26:38Z · sase-1m3.2] PROPOSED FOLLOW-UP: Add the deferred decisions-web record for durable-source statistics, machine labels, and provenance stamps — the epic decision stats_decision_record = no skipped this memory change.

[2026-10-17T03:01:53Z · sase-1m3.2] PROPOSED FOLLOW-UP: Fix the seven baseline docs-lint E5 violations in hand-written Reference pages — ToolRun 0dd0268d41e845b6bcec5c6b2123882e reported initialization.md, memory-initialization.md, core-behavior.md, memory.md, and agent-clis.md; tools/check_docs reproduced the same paths and lines on clean HEAD 7a483be1cd. No matching task was found; sase-19s covers generic extractors for different stages.

## Dependencies

- **Blocks:** [sase-1m3.8](sase-1m3.8.md) ◐ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.2/README.md) | [sase-1m3.2](sase-1m3.2.md) | 0 |
