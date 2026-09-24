# Bead: sase-17m.3.1.4 — Agent model fields

[Bead Pages](../README.md) / [sase-17m.3.1](sase-17m.3.1.md) / sase-17m.3.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.3.md) · **Assignee:** `sase-17m.3.1.4` · **Size:** medium
**Created:** 2026-09-24 02:56:47 EDT · **Closed:** 2026-09-24 09:27:25 EDT
**Plan:** [202609/agent\_session\_wire\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_wire_cutover.md)

## Description

agent-model: rename the family-concept fields of the Agent dataclass (src/sase/ace/tui/models/_agent_state.py) to agent_session* and update every src and tests reference mechanically, keeping ACE module, label, and row names for ace-cutover. Dismissed agent bundles still load the old field names.

## Notes

[2026-09-24T11:32:11Z · sase-17m.3.1.4] PROPOSED FOLLOW-UP: core-contract: teach the core artifact-index scanner (and its SQLite column/schema bump) to read agent_session_parallel, not just agent_family_parallel; stats occupancy via agent_stats_query_runs miscounts parallel members in new-spelling agent_meta.json files (see tests/stats/test_runner_occupancy_parity.py boundary comment)

[2026-09-24T13:14:40Z · sase-17m.3.1.4] agent-model work complete: renamed all 8 family-concept Agent dataclass fields to agent_session* (agent_session, agent_session_role, agent_session_parallel, is_imported/is_remote_agent_session_container, agent_session_container, imported_agent_session_parent_synthetic, derived_plan_agent_session_root) plus mirrored dataclasses (AgentListEntry, RunningAgentInfo, FamilyAttachLaunchPlan incl. env JSON round-trip, SuccessorRequest/create_kwargs), _agent_status_roles helper, plan_chain private params, and ~2400 test refs across 406 files. agent_bundle.py gained LEGACY_AGENT_FIELD_NAMES remap (old bundles load; writers emit only new; 2 new tests in tests/test_agent_model_bundle.py, proven to fail without the table). Boundaries kept per plan: core-bound capacity records keep legacy agent_family_parallel key (core struct has no alias; same boundary as capacity_session_keys_for_core), fleet/core legacy readers untouched, LEGACY_* constants untouched, cli_list -j keys + skills doc + workflow kind agent_family + launch_request agent_meta.* context keys left for runtime-cutover/durable-json (3.1.5 owns launch_request context keys). Verify: ruff clean, mypy clean (4892 files), toobig clean, committed-plans clean, thousands of scoped tests green. Pre-existing red (proven identical on clean tree b85538009, zero file overlap): symvision gate (73 private-import violations), snippet CLI x2 (rich width env), 9 prompt-panel render goldens, import-budget 3338<3290, memory-validate registry drift. Core gap filed as PROPOSED FOLLOW-UP for core-contract (index scanner misses agent_session_parallel; stats parity fixture keeps legacy parallel key with boundary comment).

[2026-09-24T13:27:25Z · sase-17m.3.1.4] Closed by explicit `sase stitch create -B close` after create_commit landed 5a048ceb3 ("refactor(agent-session): rename Agent family-concept fields to agent_session (sase-17m.3.1.4)"). The commit author requested bead completion after verifying the bead scope. Reopen with `sase bead open sase-17m.3.1.4` if more work remains.

## Dependencies

- **Depends on:** [sase-17m.3.1.3](sase-17m.3.1.3.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17m.3.1.5](sase-17m.3.1.5.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17m.3.1.6](sase-17m.3.1.6.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.3.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.4/README.md) | [sase-17m.3.1.4](sase-17m.3.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5a048ce`](https://github.com/sase-org/sase/commit/5a048ceb35cd17f2d0c56fa0586eff849ca9c535) | refactor(agent-session): rename Agent family-concept fields to agent\_session (sase-17m.3.1.4) | [sase-17m.3.1.4](sase-17m.3.1.4.md) | 2026-09-24 09:25:09 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.3.1.5][1] | check close note convention | 1 |
| read-by | [agent:sase-17m.3.1.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.5/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.3.1.land/README.md

<!-- sase:referenced-by:end -->
