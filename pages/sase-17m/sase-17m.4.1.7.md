# Bead: sase-17m.4.1.7 — Agent query dialect, CLI help, JSON output, and editor bridge

[Bead Pages](../README.md) / [sase-17m.4.1](sase-17m.4.1.md) / sase-17m.4.1.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.4.md) · **Assignee:** `sase-17m.4.1.7` · **Size:** medium
**Created:** 2026-09-24 13:32:37 EDT · **Closed:** 2026-09-24 21:51:38 EDT
**Plan:** [202609/agent\_session\_runtime\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_runtime_cutover.md)

## Description

query-cli-json: make agent query session:/kind:session canonical, with flag-gated family:/kind:family aliases. Update the CLI help text and flip the JSON output of sase agent list/search/index/wait -j and the sase editor bridge to agent_session keys and session kinds. Refresh the cli_spec snapshot, confirm sase-nvim does not branch on the old editor kinds, and declare a feat! breaking change.

## Notes

[2026-09-25T01:50:50Z · sase-17m.4.1.7] PROPOSED FOLLOW-UP: just check blocked by pre-existing base-tree failures, all reproduced identically on clean HEAD: mypy tools/sase_core_wheel_cache arg-type/var-annotated, symvision stale sase-18i epic-symbol entries (DirectApprovalOutcome/Request, execute/resolve_direct_approval already used), completion kind-coverage gate/create:next_fork (syntax-flag dropped argparse choices), completion bead-candidates-without-store. No tracking task beads found.

[2026-09-25T01:51:05Z · sase-17m.4.1.7] PROPOSED FOLLOW-UP: ace-cutover/skills-sweep leftovers outside query-cli-json scope: ACE agent_family_members module + agents-pane family relation decl/source agent_family_container + by_family mode ids/Family labels + Family detail labels + family big reveal label; plan placement family in plan_approve_render/plan_direct_approval_run/plan_direct_approval; cli_spec regen also absorbed unrelated plan-approve drift (dry-run/project options).

[2026-09-25T01:51:16Z · sase-17m.4.1.7] PROPOSED FOLLOW-UP: agents_sync does not consume AgentCatalogRow kinds (no import site), so no family-mapping was needed at the agents_sync boundary; registries may still store container_kind family until rebuild, accepted by _derive.

[2026-09-25T01:51:38Z · sase-17m.4.1.7] feat(agent-session)!: agent-session query syntax, CLI help, and JSON output (sase-17m.4.1.7). Verified: 317 focused tests green (catalog/search/live-query/editor/wait/list/index/parser/pushdown suites); just fix clean; cli_spec regenerated; sase-nvim has no famil hits and does not branch on old editor kinds; epic-symbols clean. just check blocked only by 4 pre-existing base-tree failures reproduced identically on clean HEAD (recorded as PROPOSED FOLLOW-UP notes). BREAKING CHANGE: agent list -j agent_family/agent_family_role -> agent_session/agent_session_role; agent search -j family -> agent_session and kind family -> session; agent index dismissed_family_* -> dismissed_agent_session_*; agent wait -j kind family -> session; editor bridge kind family -> session with session N members detail; agent queries use session:/kind:session with family:/kind:family as flag-gated aliases.

## Dependencies

- **Depends on:** [sase-17m.4.1.6](sase-17m.4.1.6.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17m.4.1.8](sase-17m.4.1.8.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.4.1.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.7/README.md) | [sase-17m.4.1.7](sase-17m.4.1.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3a1d0ba`](https://github.com/sase-org/sase/commit/3a1d0bab282a5d796d9b2d8f45ab4a65c96f4091) | feat(agent-session)!: canonical session query dialect with JSON kinds | [sase-17m.4.1.7](sase-17m.4.1.7.md) | 2026-09-24 21:54:27 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.4.1.7][1] | Need the phase scope and design file | 2 |
| read-by | [agent:sase-17m.4.1.8][2] | Check PROPOSED FOLLOW-UP notes from earlier phases | 1 |
| read-by | [agent:sase-17m.4.1.land][3] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.7/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.8/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.land/README.md

<!-- sase:referenced-by:end -->
