# Bead: sase-ru.9 — Resolve the planner-chat experiment into a durable behavior

[Bead Pages](../README.md) / [sase-ru](README.md) / sase-ru.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09i](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09i.md) · **Assignee:** `sase-ru.9` · **Size:** medium
**Created:** 2026-08-21 10:44:30 EDT · **Closed:** 2026-08-21 12:12:42 EDT
**Plan:** [202608/open\_feature\_flag\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/open_feature_flag_closeout.md)

## Description

planner_chat_retirement: apply the approved planner-chat disposition, remove coder_inherits_planner_chat, and close its bead with the trial evidence and decision recorded.

## Notes

[2026-08-21T15:51:59Z · sase-ru.9] Applied the sase-ru.4 trial recommendation: abandon coder_inherits_planner_chat and keep unconditional plan-file-only coder handoff. Removed FeatureFlag.coder_inherits_planner_chat, the #fork resume_prefix in run_agent_exec_plan_accept, registry/schema/help/docs references, and the On-state follow-up tests. Follow-up coder prompts now always start from @plan with no planner chat. tools/check_feature_flags --static passed. Focused tests: test_axe_run_agent_exec_plan_followup_coder_prompt, test_consumers, test_schema, test_global_options, test_parser_root_help, test_candidates_providers (85 passed).

[2026-08-21T16:11:17Z · sase-ru.9] PROPOSED FOLLOW-UP: ruff F601 duplicate catalog key — src/sase/telemetry/catalog.py repeats "sase_finalizer" and fails just _lint-ruff on this tree; not caused by planner-chat retirement.

[2026-08-21T16:11:44Z · sase-ru.9] PROPOSED FOLLOW-UP: check_feature_flags rule 8 for sase-rc — live flag bead sase-rc has no artifact_links definition (created 2026-08-20 by sase-r8.3); excluded from this epic and not touched here.

[2026-08-21T16:12:14Z · sase-ru.9] PROPOSED FOLLOW-UP: Config pane tests vs ConfigHubPane — ACE tests/ace/tui/test_config_pane_widget*.py expect ConfigPane at #config but find ConfigHubPane; 30+ failures on the escalated full suite, unrelated to planner-chat retirement.

[2026-08-21T16:12:42Z · sase-ru.9] Abandoned coder_inherits_planner_chat (sase-qe closed canceled). Coder follow-up in run_agent_exec_plan_accept is unconditional plan-file-only: no #fork resume_prefix. Removed registry/schema/help/docs and On-state tests. Verified: tools/check_feature_flags --static; .venv/bin/sase flag list has no coder_inherits_planner_chat; 85 focused tests passed; just fmt-py, fmt-md, mypy, and ruff on touched files passed. No leftover --epic-symbol entries. just check is red on unrelated HEAD issues (ruff F601 catalog.py, sase-rc rule 8, ConfigHubPane tests); scoped run escalated (schema/registry) and the full suite was 35623 passed / 64 failed with none in the planner-chat follow-up, flag-consumer, or help tests this phase owns.

## References

- file:explicit:0b50eb32321cc48fb8e48e7b

## Dependencies

- **Blocks:** [sase-ru.12](sase-ru.12.md) ◐ · ⧖ 2026-08-21
- **Depends on:** [sase-ru.4](sase-ru.4.md) ✓ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ru.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ru.9/README.md) | [sase-ru.9](sase-ru.9.md) | 0 |
