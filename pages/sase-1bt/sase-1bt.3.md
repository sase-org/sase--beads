# Bead: sase-1bt.3 — Python adapter, state vocabulary, beta flag, shared log tail, and the chop glyph move

[Bead Pages](../README.md) / [sase-1bt](README.md) / sase-1bt.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tc.md) · **Assignee:** `sase-1bt.3` · **Size:** medium
**Created:** 2026-09-27 18:32:37 EDT · **Closed:** 2026-09-27 22:39:42 EDT
**Plan:** [202609/tool\_runs\_tui\_surfaces.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_runs_tui_surfaces.md)

## Description

tool-run-adapter: move the core pin, add typed Python adapters and binding registrations, the ToolRun view vocabulary, the ace_tool_runs beta flag, a shared pure log-tail helper used by the CLI, and move the chop link-trail icon from ⚒ to ⏲.

## Notes

[2026-09-28T01:47:33Z · sase-1bt.3] PROPOSED FOLLOW-UP: sync sase wire mirrors past sase-core artifact-index schema 34 — tests/core/test_agent_alias_history_wire.py and test_agent_output_variable_history_wire.py pin AGENT_ARTIFACT_INDEX_SCHEMA_VERSION == 33 but the current sase-core checkout reports 34; fails identically without this phase diff (untouched files), owned by whichever epic moved the core checkout

[2026-09-28T02:39:05Z · sase-1bt.3--1] PROPOSED FOLLOW-UP: full check 56471cbd76a6995bcc4e14554fa9d36f shows 32 failures, all reproduce without this phase diff — 30/31 re-ran FAILED on the stashed clean base tree (/tmp/base_check.log: agent_completion x9, directive_completion x2, repeat_env x6, completion snapshot x2 + kind_coverage, config_schema receipt-vs-schema, app_import_budget, prompts_overlay, header_panel, watch_highlighted, timezone guard, docs wording, marker-path audit, 2 wire pins); test_plan_filter_query_round_trip is a hypothesis FlakyFailure and zsh sbd smoke passes in isolation with the diff. Owned by whichever epics own those areas, not sase-1bt.3

[2026-09-28T02:39:42Z · sase-1bt.3--1] tool-run-adapter done: core pin to bc71eb2, typed adapters in core/tool_run.py, view vocabulary in tool/view_vocabulary.py, ace_tool_runs beta flag (registry+schema+flag helper), shared tool_run_log_tail in tool/logs.py wired into query replay, chop glyph U+2692->U+23F2 with link tests updated, 23 symbols whitelisted under parent epic key sase-1bt. Verified: 112 phase tests pass; ruff/mypy/flags/keep-sorted/fmt green; full check 56471cbd76a6995bcc4e14554fa9d36f — all 32 failures reproduce on clean base tree or are isolation-passing flakes (see bead notes), none from this diff.

## Dependencies

- **Depends on:** [sase-1bt.1](sase-1bt.1.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bt.4](sase-1bt.4.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bt.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bt.3.md) | [sase-1bt.3](sase-1bt.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5c54e6c`](https://github.com/sase-org/sase/commit/5c54e6c14b641766c60349dc095ec4a63a092755) | feat(tool-runs): typed adapters, view vocabulary, beta flag, shared log tail, chop glyph move (sase-1bt.3) | [sase-1bt.3](sase-1bt.3.md) | 2026-09-27 22:42:38 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bt.3--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bt.3.md

<!-- sase:referenced-by:end -->
