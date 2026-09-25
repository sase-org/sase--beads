# Bead: sase-17m.4.1.5 — Core mirrors, chat fork, scripts, and remaining non-ACE packages

[Bead Pages](../README.md) / [sase-17m.4.1](sase-17m.4.1.md) / sase-17m.4.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.4.md) · **Assignee:** `sase-17m.4.1.5` · **Size:** medium
**Created:** 2026-09-24 13:32:34 EDT · **Closed:** 2026-09-24 19:10:39 EDT
**Plan:** [202609/agent\_session\_runtime\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_runtime_cutover.md)

## Description

core-history: rename history/chat_fork/family.py and scripts/_agent_chat_from_name_family.py and the family-concept identifiers in src/sase/core (keeping core-emitted legacy values as named mirrors), history, scripts, stats, ops, sdd (except sidecar paths), llm_provider, workspace_provider, config/_settings_runner.py, sase_agent.py (except the families/ URL), main internals, xprompt internals, and the remaining top-level modules.

## Notes

[2026-09-24T23:09:47Z · sase-17m.4.1.5] PROPOSED FOLLOW-UP: core-contract flip must also rename these Python mirrors of core-emitted legacy values (each already carries a "legacy agent-family spelling" marker): core/agent_identity_facade.py (_AgentLinkTargetKind.LEGACY_AGENT_FAMILY = "family" — renamed here from FAMILY, value kept; payload["family_name"] fallback in parse_agent_session_name/_parse_owned_agent_name); core/agent_cleanup_wire.py cleanup_targets_for_core and core/runner_slots/_admission_capacity_records.py (both send agent_family_parallel); core/agent_cleanup_python.py skip reason "parallel family still active" (byte-identical to the Rust planner); core/agent_launch_wire_from_dict.py (family_attach_<field> reads); gate_shell/handoff.py (sends "family_name"); dispatch/launch.py (family_id logical key); axe/run_agent_wait_slot_candidate.py (payload "family" deadlock-node key); stats/query.py RuntimeGroupBy "family" + LEGACY_RUNTIME_GROUP_BY and stats/_view_builders.py group_by normalisation; agent/names/_registry_batch.py ("family" predicates), _registry_entries.py LEGACY_AGENT_FAMILY_CONTAINER_KIND, _registry_group_mutations.py; agent/wait_watch/_types.py AGENT_SESSION = "family" (query-cli-json also owns it); agents/catalog/_derive.py (emits "family"). Fork-source kind "family" (history/chat_fork/common.py LEGACY_FORK_SOURCE_KIND, core/wait_dependency_resolution/_index_fork_queries.py, continuation_baseline.py) is Python-owned durable data: permanent legacy reader, not a core-contract item.

[2026-09-24T23:09:59Z · sase-17m.4.1.5] PROPOSED FOLLOW-UP: skills-sweep classification hand-off for src outside ACE: (syntax-flag) family= keyword text still in xprompt/_directive_edit_identity.py (emits family=, {"clan","family"} conflict check), xprompt/_directive_collect.py:541, xprompt/workflow_loader_definition.py removed-kind message, monitor/followup.py docstring (%id(<suffix>, family=<parent>)), agent/relaunch_prompt.py ("cannot rewrite a family member..."/"family rewrite is missing..." errors), main/parser_gate.py --next-fork choices; (query-cli-json) parser help text in main/parser_agent_hold.py, parser_agent_lifecycle.py, parser_agent_search.py, parser_gate.py, parser_monitor.py, parser_pipe.py and pipe_handler.py output copy, agents/cli_index.py messages, integrations/_editor_helper_agents.py detail text; (ace-cutover) src/sase/default_config.yml and config/sase.schema.json family wording, and the comment in agent_session_plan_preview.py that names ACE module agent_family_preview_cache; (session-pages) sase_agent.py + sdd/hosted_links.py "families/" URLs, sdd/_init_files.py, sdd/templates/sidecar-agents-README.md, sdd/assets/agents-directory-map.png.prompt.md. Tests still carrying family-concept names (not renamed here; ~1.3k hits across ~240 files outside tests/ace, tests/perf, tests/agents_sync) include test_editor_helper_family_catalog.py, test_fold_filtering.py, test_agent_name_wipe.py, test_agent_clan.py, test_agent_loader_status_override_*family*.py, test_agent_loader_dedup_pid_families.py, test_directives_family.py, test_plan_chain_agent_session_keys.py, test_agent_session_*.py, the test_dynamic_agent_session_attach_* bodies, and the tests/test_core_facade legacy-key fixtures.

[2026-09-24T23:10:11Z · sase-17m.4.1.5] PROPOSED FOLLOW-UP: pre-existing failures on the clean HEAD tree (verified in a worktree; not caused by this phase): mypy (15 errors in ace/tui/widgets/_agent_detail_*.py and ace/tui/command_line/{input,screen}.py), symvision (_dispatch_preview_source_summary in ace/tui/widgets/_prompt_input_bar_dispatch.py), toobig (ace/tui/command_line/screen.py, ace/tui/widgets/decks/panel.py), lint test-waits (tests/ace/tui/command_line/test_completion_popup.py:181), and ~30 tests (keymaps help, agent-prompt-panel, timezone guard, test_config_schema, axe wait_checks deferred_unconfirmed summary, test_llm_provider_effort_invocation, snippet CLI path wrapping). This phase fixed the two stale-from-agent-runtime tests it hit (tests/ace/tui/test_kill_and_edit_prompt_name.py kwargs, tests/test_launch_approval.py message).

[2026-09-24T23:10:39Z · sase-17m.4.1.5] Renamed history/chat_fork/family.py -> agent_session.py and scripts/_agent_chat_from_name_family.py -> _agent_chat_from_name_agent_session.py (plus ForkAgentSessionMemberSource/ForkExcludedAgentSessionMember, format_agent_session_fork_source, find_agent_session_member, read_agent_session_monitor_marker, rewrite_prompt_agent_session_member_name, SaseAgentRef.is_agent_session); fork sources now emit kind 'session' (legacy 'family' still read, tested); core mirror _AgentLinkTargetKind.FAMILY -> LEGACY_AGENT_FAMILY (value kept); bead cleanup membership/messages, history/sdd/llm_provider/workspace_provider/xprompt/main-internal/doctor prose moved to agent-session; renamed 3 chat-from-name test files and concept test names in wait-dependency/stats/sdd/history/core_facade/runner_slots tests, added legacy-kind tests. Verified: just fix clean; ruff, feature-flags, pyscripts, changelog, terminology, validate, committed-plans pass; symvision/toobig/test-waits/mypy failures are pre-existing on clean HEAD (ACE files only, verified in a worktree); test-scoped ran the full lane: only failures are pre-existing on clean HEAD, plus the one new expected-text failure (test_fork_workflow) which I fixed; epic-symbols reports no entries. Follow-up notes recorded on the bead.

## Dependencies

- **Depends on:** [sase-17m.4.1.4](sase-17m.4.1.4.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-17m.4.1.6](sase-17m.4.1.6.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.4.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.5/README.md) | [sase-17m.4.1.5](sase-17m.4.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`33e41c7`](https://github.com/sase-org/sase/commit/33e41c72e2d3ed445864bfe5d932e370ac0207d4) | refactor(agent-session): rename core mirrors, chat fork, and scripts identifiers (sase-17m.4.1.5) | [sase-17m.4.1.5](sase-17m.4.1.5.md) | 2026-09-24 19:11:45 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-17m.4.1.5][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-17m.4.1.8][2] | Check PROPOSED FOLLOW-UP notes from earlier phases | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.5/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.4.1.8/README.md

<!-- sase:referenced-by:end -->
