# Bead: sase-ha.4 — Usage, tool-call, and model-identity artifacts

[Bead Pages](../README.md) / [sase-ha](README.md) / sase-ha.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ve](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ve/README.md) · **Assignee:** `sase-ha.4` · **Size:** medium
**Created:** 2026-08-07 20:45:54 EDT · **Closed:** 2026-08-07 21:42:59 EDT
**Plan:** [202608/muse\_provider.md](https://github.com/sase-org/sase--plans/blob/main/202608/muse_provider.md)

## Description

artifacts: extract tool calls from the Muse event stream, recover token usage from the session log SASE owns via `--session-id`, and record the model Muse actually configured.

## Notes

[2026-08-08T01:41:01Z · sase-ha.4] PROPOSED FOLLOW-UP: project Muse session-lifetime subagents into ACE — the stream carries task.stream.linked, per-subagent subagent/<uuid>/session.jsonl dirs, and goal_usage_attribution.owner.{owner_type,requester_kind} distinguishing main_root from subagent usage, so SASE could stop counting a whole Muse fan-out as one agent.

[2026-08-08T01:41:41Z · sase-ha.4] PROPOSED FOLLOW-UP: investigate Muse's cron_* tools and per-session cron.db — check whether they can schedule work that outlives a SASE invocation, and decide whether SASE must disable or reconcile them.

[2026-08-08T01:42:19Z · sase-ha.4] PROPOSED FOLLOW-UP: tests/doctor/test_checks_providers.py::test_setup_hint_points_script_installs_at_the_install_subcommand fails on clean master (verified with git stash) — the script-manager branch of setup_hint from the cli_meta phase is missing; not caused by this phase.

[2026-08-08T01:42:59Z · sase-ha.4] Implemented the artifacts phase: _tool_call_muse.py (task.lifecycle proposed/scheduled/side_effect_intent/output + tool.result state machine, tool.-prefixed task kinds only, targets from edit_facts.path -> bash result command/description -> bounded result preview), _muse_session_usage.py (usage summed from model_completed events in the globbed session log, XDG_DATA_HOME honored, goal_usage_attribution ignored to avoid double-counting, missing/unreadable log degrades to zeroed usage + diagnostic), run_metadata.json capture of run.model.configured model_id/provider_id, and --session-id threaded from muse.py into the parser. Verified: 17 new tests in tests/llm_provider/test_muse_artifacts.py all pass off the R708.1 fixtures (read/write/bash records, non-tool tasks producing nothing, pending call finalized via finalize_pending_tool_calls, usage == 48093/479/0/31650, double-count avoidance, missing log, model identity, argv-vs-parser session id); full tests/llm_provider suite green; just lint fully green including symvision and toobig; just check green apart from a pre-existing failure on clean master (tests/doctor/test_checks_providers.py::test_setup_hint_points_script_installs_at_the_install_subcommand, noted as a follow-up).

[2026-08-08T01:43:45Z · sase-ha.4] Muse tool-call parsing, session-log usage attribution, and run model metadata: 17 new tests in tests/llm_provider/test_muse_artifacts.py off the R708.1 fixtures (usage sums to 48093/479/0/31650, double-count regression, argv session-id handle); full tests/llm_provider suite and just lint green. One pre-existing unrelated failure in tests/doctor/test_checks_providers.py confirmed on clean master via git stash.

## Dependencies

- **Depends on:** [sase-ha.2](sase-ha.2.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-ha.7](sase-ha.7.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ha.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ha.4/README.md) | [sase-ha.4](sase-ha.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`050c947`](https://github.com/sase-org/sase/commit/050c9477cea1e11b85df7d504b46a50db3bbdd67) | feat(llm-provider): parse Muse tool calls, usage, and model identity | [sase-ha.4](sase-ha.4.md) | 2026-08-07 21:44:51 EDT |
