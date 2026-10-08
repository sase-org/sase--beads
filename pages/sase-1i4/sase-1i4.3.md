# Bead: sase-1i4.3 — Orphaned agent scope reaper job

[Bead Pages](../README.md) / [sase-1i4](README.md) / sase-1i4.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.5s](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.5s.md) · **Assignee:** `sase-1i4.3` · **Size:** medium
**Created:** 2026-10-08 06:37:36 EDT · **Closed:** 2026-10-08 09:48:11 EDT
**Plan:** [202610/agent\_scope\_leak\_reaping.md](https://github.com/sase-org/sase--plans/blob/main/202610/agent_scope_leak_reaping.md)

## Description

scope-reaper: add a checks-routine job that discovers sase-agent scopes with no live runner and sweeps their non-spared processes, with a dry-run core API, docs, and a live systemd test.

## Notes

[2026-10-08T13:26:25Z · sase-1i4.3--3] PROPOSED FOLLOW-UP: symvision unused-public debt predates this phase (8 symbols fail just _lint-symvision identically with phase work stashed: BeadStoreFingerprint, HumanText, InstructionManifestError in core/instruction_manifest, aggregate_rows, git_remote_tracking_ref, macro_input_choice_to_wire, prune_cache_entries, finalizer_owned_monitor_refusal); needs owner triage or baseline refresh

[2026-10-08T13:47:54Z · sase-1i4.3--4] PROPOSED FOLLOW-UP: symvision unused-public backlog still red after scope-reaper (63 items; 59 byte-identical on clean base via git stash -u comparison, base has 62; phase removed execute_scope_sweep/read_scope_members/ScopeSweepResult via privatization and added plan-mandated reaper API AgentScope/ReapedScope/ReapResult/discover_agent_scopes, entry point reap_orphaned_agent_scopes consumed by orphan_agent_scope_reap chop; triage NEW labels on untouched files are witness lag); tracked by backlog bead sase-1hp

[2026-10-08T13:48:11Z · sase-1i4.3--4] scope-reaper done: orphan_agent_scope_reap chop job (checks routine, 300s cadence) with dry-run core API reap_orphaned_agent_scopes/discover_agent_scopes, docs, console scripts; verified 75 phase tests pass, ruff+format clean, _lint-test-waits green, epic-symbols empty with all 7 phase --epic-symbol rows dropped from Justfile; _lint-symvision still lists 63 unused-public (59 byte-identical on clean base, tracked by sase-1hp; 4 new are plan-mandated API) so check stays red on base debt only

## Dependencies

- **Depends on:** [sase-1i4.2](sase-1i4.2.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1i4.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1i4.3.md) | [sase-1i4.3](sase-1i4.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a10a6c6`](https://github.com/sase-org/sase/commit/a10a6c60352667d856f4c697134ba4df5fa243a1) | feat(scope): reap orphaned agent scopes with checks-routine backstop job | [sase-1i4.3](sase-1i4.3.md) | 2026-10-08 09:50:02 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1i4.3--4][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1i4.land][2] | Need proposed follow-up notes before close | 2 |
| read-by | [agent:toobig-7d.agent_list_entry_builder.0--2][3] | Confirm bead closed before filing stale-whitelist follow-up | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1i4.3.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1i4.land/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.toobig-7d.agent_list_entry_builder.0.md

<!-- sase:referenced-by:end -->
