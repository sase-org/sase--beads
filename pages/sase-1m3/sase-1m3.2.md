# Bead: sase-1m3.2 — Per-project linked-repo resolution and declared-by provenance

[Bead Pages](../README.md) / [sase-1m3](README.md) / sase-1m3.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.1s.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.1s.linker.w0.md) · **Assignee:** `sase-1m3.2` · **Size:** medium
**Created:** 2026-10-16 22:05:21 EDT · **Closed:** 2026-10-16 23:02:50 EDT
**Plan:** [202610/sase\_stats\_project.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_stats_project.md)

## Description

inventory: fix sase-1lk so another project's linked repos never absorb the cwd project's entries, and record whether each linked repo was declared by the project or by user-wide config.

## Notes

[2026-10-17T02:26:26Z · sase-1m3.2] PROPOSED FOLLOW-UP: Reuse RepoRecord.declared_by in sase-1l2 — the stats loader can classify project-declared versus user-linked repos without name heuristics.

[2026-10-17T02:26:38Z · sase-1m3.2] PROPOSED FOLLOW-UP: Add the deferred decisions-web record for durable-source statistics, machine labels, and provenance stamps — the epic decision stats_decision_record = no skipped this memory change.

[2026-10-17T03:01:53Z · sase-1m3.2] PROPOSED FOLLOW-UP: Fix the seven baseline docs-lint E5 violations in hand-written Reference pages — ToolRun 0dd0268d41e845b6bcec5c6b2123882e reported initialization.md, memory-initialization.md, core-behavior.md, memory.md, and agent-clis.md; tools/check_docs reproduced the same paths and lines on clean HEAD 7a483be1cd. No matching task was found; sase-19s covers generic extractors for different stages.

[2026-10-17T03:02:50Z · sase-1m3.2] Implemented per-project config resolution and declared_by inventory/JSON provenance; closed sase-1lk after regression coverage. The 22 focused resolver, inventory, repo-list, and config-cache tests passed. sase tool run check stopped at docs contract on seven E5 violations, reproduced identically by tools/check_docs on clean HEAD 7a483be1cd; follow-up recorded. epic-symbols reported none.

## Dependencies

- **Blocks:** [sase-1m3.8](sase-1m3.8.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1m3.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.2/README.md) | [sase-1m3.2](sase-1m3.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7c6b324`](https://github.com/sase-org/sase/commit/7c6b32457bdc26d6dda8362c93774b17c5550c23) | feat(repo): resolve linked repo config by target path | [sase-1m3.2](sase-1m3.2.md) | 2026-10-16 23:06:03 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1lh.7.5.4.3.1][1] | Need whether config-loader phase already fixed stale tests | 1 |
| read-by | [agent:sase-1m3.2][2] | Verify recorded follow-ups and phase status before closure | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1lh.7.5.4.3.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1m3.2/README.md

<!-- sase:referenced-by:end -->
