# Bead: sase-1qz.9 — The recovery panel

[Bead Pages](../README.md) / [sase-1qz](README.md) / sase-1qz.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.apollo.research.33.linker.w0` · **Assignee:** `sase-1qz.9` · **Size:** medium
**Created:** 2026-11-02 17:42:17 EST
**Plan:** [202611/agent\_hijack.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack.md)

## Description

tui_panel: extend AgentActionChooserModal with a header, single-line sectioned rows, disabled rows with reasons, a pending preview state, and an Enter arming delay. Route Enter on HIJACKED to the panel and wire u/c/r/v/t/d plus x-to-dismiss through durable procs, with 80x24 visual snapshots.

## Notes

[2026-11-06T21:30:50Z · sase-1qz.9--1] PROPOSED FOLLOW-UP: reconcile the linked sase-core compatibility schema before just check (sase tool run 299cbe71962e096b41f7ee593000de7b rebuilt the refreshed core, then tools/validate_sase_core_rs reported agent_artifact_run_trash_wire_schema_version got 2, expected 1; direct validator rerun reproduced it, and the validator is unchanged from the base tree; broader stale-core-schema evidence is already tracked in sase-1gu.6 note #1).

## Dependencies

- **Blocks:** [sase-1qz.10](sase-1qz.10.md) ◐ · ⧖ 2026-11-02
- **Depends on:** [sase-1qz.7](sase-1qz.7.md) ✓ · ⧖ 2026-11-02
- **Depends on:** [sase-1qz.8](sase-1qz.8.md) ✓ · ⧖ 2026-11-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qz.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1qz.9.md) | [sase-1qz.9](sase-1qz.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a6ceb8b`](https://github.com/sase-org/sase/commit/a6ceb8bf930fee6654b74c7f5aba5c27d747226b) | feat(ace): add hijack recovery panel | [sase-1qz.9](sase-1qz.9.md) | 2026-11-06 16:34:33 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:18n][1] | Check in-progress hijack phase notes for deviations from the plan, for a user-facing report | 1 |
| read-by | [agent:research.3a.final][2] | Check active epic phase scopes for conflict screening of task bead recommendations | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.18n/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.3a.final/README.md

<!-- sase:referenced-by:end -->
