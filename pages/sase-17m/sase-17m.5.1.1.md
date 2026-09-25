# Bead: sase-17m.5.1.1 — ACE model modules and Agent identifiers

[Bead Pages](../README.md) / [sase-17m.5.1](sase-17m.5.1.md) / sase-17m.5.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.md) · **Assignee:** `sase-17m.5.1.1` · **Size:** medium
**Created:** 2026-09-25 00:06:02 EDT · **Closed:** 2026-09-25 01:20:38 EDT
**Plan:** [202609/agent\_session\_ace\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_ace_cutover.md)

## Description

models: rename the family-named modules in src/sase/ace/tui/models/ (_agent_imported_family, _agent_parallel_family, _agent_status_family{,_core,_planner,_policy}, _family_shell_membership, agent_family_members, agent_family_preview_cache). Also rename their classes and functions, the family-concept Agent methods and properties (is_family_member_child, family_reference_name, presented_family_reference_name), AgentChildLinkage.FAMILY_MEMBER, and the family identifiers in agent_groups, agent_tribe_summary, agent_nodes, agent_bundle, clan, loaders, and fleet-agents models. Core-emitted legacy keys stay as marked readers. Update every importer, in or outside ACE, and rename the matching tests/ace/tui/models tests and helpers.

## Notes

[2026-09-25T05:18:05Z · sase-17m.5.1.1] PROPOSED FOLLOW-UP: just lint/check gates fail identically on clean base — tools/smoke_sase_core_rs_tool_runs:75 mypy var-annotated, symvision unused-publics (CoderPlacement/PlanGateHistory/RetiredGate/gather_*/tool_run_*), toobig tests/tool/test_settlement.py 1048 lines; no tracking task bead found

[2026-09-25T05:18:23Z · sase-17m.5.1.1] PROPOSED FOLLOW-UP: tribe/clan roster kind text now renders "session" (was "family"); confirm PNG goldens covering entry-indicator/roster kind text in copy or snapshots-sweep (non-PNG test_agent_panel_entry_indicator updated)

[2026-09-25T05:18:34Z · sase-17m.5.1.1] PROPOSED FOLLOW-UP: shared fleet_summary fixture still emits only legacy family_id/family_role/family_label keys, so fleet new-key-first reads lack fixture coverage; consider a new-shape fleet fixture in snapshots-sweep or core-contract

[2026-09-25T05:20:38Z · sase-17m.5.1.1] 9 model modules git-mv'd with classes/functions; Agent props/methods, AGENT_SESSION_MEMBER=session_member (unp persisted), tribe unit kind session, fleet new-key-first reads with marked legacy readers; all importers updated. Verified: 836 models tests, 544 targeted/importer tests, 3663-test ACE sweep (1 fallout fixed: entry-indicator kind text ns session); ruff, main mypy, terminology audit pass. lint/check gates fail identically on clean base (follow-ups noted); no epic-symbols left

## Dependencies

- **Blocks:** [sase-17m.5.1.2](sase-17m.5.1.2.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.5.1.1/README.md) | [sase-17m.5.1.1](sase-17m.5.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`09e0571`](https://github.com/sase-org/sase/commit/09e0571475add947cf30fc2db0eb48ef089c7dfc) | refactor(ace): rename agent-family model modules and identifiers to agent session (sase-17m.5.1.1) | [sase-17m.5.1.1](sase-17m.5.1.1.md) | 2026-09-25 01:23:00 EDT |
