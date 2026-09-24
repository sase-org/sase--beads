# Bead: sase-17m.4.1.2 — Name lookup, plan\_chain, and plan preview

[Bead Pages](../README.md) / [sase-17m.4.1](sase-17m.4.1.md) / sase-17m.4.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.4.md) · **Assignee:** `sase-17m.4.1.2` · **Size:** medium
**Created:** 2026-09-24 13:32:30 EDT
**Plan:** [202609/agent\_session\_runtime\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_runtime_cutover.md)

## Description

names-preview: rename the family-concept identifiers in agent/names/ (find_agent_family, agent_family_base, reserved-name and forced-reuse helpers) and plan_chain.py, and delete the deprecated AGENT_FAMILY_* aliases. Rename agent_family_plan_preview.py to agent_session_plan_preview.py along with its types. Update every importer, including ACE imports only, and the tests.

## Notes

[2026-09-24T19:22:15Z · sase-17m.4.1.2] PROPOSED FOLLOW-UP: pre-existing mypy errors at HEAD in src/sase/ace/tui/widgets/_agent_detail_display.py and _agent_detail_state.py (AgentDetailDisplayMixin/AgentDetailStateMixin missing _sync_header_visibility, query_one, update_display); untouched by names-preview, just check stays red until fixed

[2026-09-24T19:34:21Z · sase-17m.4.1.2] PROPOSED FOLLOW-UP: three pre-existing test failures at HEAD unrelated to names-preview (verified failing on clean stash): completion test_bead_candidates_without_a_store_returns_empty_list (live bead-state leakage), completion test_every_value_slot_is_kinded_choiced_or_hinted (tool/stop + tool/wait slots), restart test_wipe_failed_exits_1_and_prints_recovery_dir (recovery-dir name assert)

## Dependencies

- **Depends on:** [sase-17m.4.1.1](sase-17m.4.1.1.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17m.4.1.3](sase-17m.4.1.3.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.4.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.2/README.md) | [sase-17m.4.1.2](sase-17m.4.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`786539e`](https://github.com/sase-org/sase/commit/786539e6a67d8c134a7469d931089dcec2c8785c) | refactor(agent-session): name lookup, plan\_chain, and plan preview (sase-17m.4.1.2) | [sase-17m.4.1.2](sase-17m.4.1.2.md) | 2026-09-24 15:35:42 EDT |
