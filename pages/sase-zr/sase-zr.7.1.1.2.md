# Bead: sase-zr.7.1.1.2 — Receipt-scoped journal, truthful attempt completion and durable failure outcomes

[Bead Pages](../README.md) / [sase-zr.7.1.1](sase-zr.7.1.1.md) / sase-zr.7.1.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-zr.7.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-zr.7.1.md) · **Assignee:** `sase-zr.7.1.1.2` · **Size:** medium
**Created:** 2026-09-17 06:47:33 EDT · **Closed:** 2026-09-17 11:13:42 EDT
**Plan:** [202609/gate\_decision\_integrity\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/gate_decision_integrity_1.md)

## Description

failure_journal: in sase, adopt the new core revision, stamp every receipt and journal lifecycle event with an acceptance id, record a redacted attempt_failed outcome for command, terminal_prepare, side_effects and follow_up failures, journal attempt_completed only after response.json is published, make resume retry only archive/terminal preparation or failed side effects without re-running completed commands, and keep legacy early-completed journals resumable.

## Notes

[2026-09-17T15:09:56Z · sase-zr.7.1.1.2] PROPOSED FOLLOW-UP: test suite shows intermittent unrelated flakes under full just check parallel load — saw test_rendered_link_contract, test_models_panel_effort, and test_suite_gate_scaled_integration (AF_UNIX path length) each fail once across 3 full runs, all passing in isolation on an unchanged tree; worth a flake-rate audit if this recurs.

[2026-09-17T15:10:54Z · sase-zr.7.1.1.2] PROPOSED FOLLOW-UP: the plan named tests/test_plan_approval_actions_archive.py and tests/test_plan_archive_approval_recovery.py for archive-failure/resume coverage; I covered the same terminal_prepare-failure/resume mechanics generically in the new tests/test_gate_execution_failure_outcomes.py instead (those two files test lower-level git-archive plumbing that does not exercise the journal/failure-outcome path directly) — a future agent could add a plan-gate-specific integration test there for full parity if wanted.

[2026-09-17T15:11:47Z · sase-zr.7.1.1.2] Implemented: acceptance_id minted on every accepted/superseding decision.py request; journal.py gained acceptance_id/stage/message/outcome_id/error_record fields, attempt_resumed/stage_started/stage_completed/attempt_failed events, response-exists-scoped incomplete_attempt (fixes legacy early-attempt_completed resumability), and current_execution_failure/current_post_response_failure reducers. New failure_outcome.py (record_failure_outcome, recorded_attempt_failure, with_follow_up_stage_tracking) centralizes redacted (1000-char, secret-scrubbed) attempt_failed recording reusing the existing errors/*.json record (command_runner.record_execution_error now tags stage/attempt_id/outcome_id and returns the relative path — no parallel store). New attempts.py holds begin_attempt/execute_one_option, moved out of executor.py to stay under the toobig FYI threshold (642 lines). executor.py now: journals attempt_completed only after response.json is written, stage_started/stage_completed brackets terminal_prepare and side_effects, resumes only the failed stage (side_effects-only resume added with launch-id skip guards in adapters.py for task_triage/flag_triage/epic-launch). cli_answer.py and plan_approval_actions.py bracket their settle_gate_shell calls with the follow_up stage and, in _resume_answered_shell, rerun side effects first when a side_effects failure is current. gate_decision_facade.py + gate_shell/lifecycle.py gained the claim_gate_decision_execution facade and accepted_failed/accepted_owner_lost disposition mirrors for owner_conflict to wire up next (whitelisted with --epic-symbol keyed to sase-zr.7.1.1.3, since nothing in this phase calls them yet).

[2026-09-17T15:12:35Z · sase-zr.7.1.1.2] sase-core adoption: sase-core-revision.txt ratcheted to b4c3ca63662ce2199b1af652eaebcc3946bb8b29 (feat(gate-decision): add execution owner recovery policy — the landed core_execution_policy commit; note its actual wire shapes differ from the plan draft, e.g. GateDecisionExecutionOwnerWire is untagged legacy-string-or-structured-record, GateDecisionExecutionFactsWire has no post_response_failure field, and GateLifecycleDecisionWire has no owner_liveness/failure echo — this phase followed the landed contract). Confirmed via PyPI JSON API that sase-core-rs v0.34.42 (containing that commit) is published, so raised the pyproject.toml floor from >=0.34.37 to >=0.34.42,<0.35.0 per the plans raise-only-if-published rule; just install confirms the binding exposes claim_gate_decision_execution. Unrelated: fixed a stale tests/test_config.py reference in tests/test_proc_env_isolation.py (the file was split into tests/test_config_merge.py etc. in an earlier commit) since it was blocking just check for any diff touching tests/test_gate_cli_answer.py.

[2026-09-17T15:13:42Z · sase-zr.7.1.1.2] Verified: sase memory read lint_and_test.md; just fix; just check run to completion twice pre-refactor (42445 and 42448 passed, 22 skipped, only isolated unrelated flakes each run — test_rendered_link_contract and test_models_panel_effort, both confirmed passing on an unchanged tree in isolation) plus a post-refactor sweep (ruff/mypy/symvision/toobig individually green, 2234 gate/plan-approval-filtered tests passed with one more unrelated environmental flake in test_suite_gate_scaled_integration, an AF_UNIX path-length artifact of this workspace's long tmp path). sase bead epic-symbols sase-zr.7.1.1.2 is empty; the two forward-looking symbols (claim_gate_decision_execution, current_execution_failure) are whitelisted via --epic-symbol keyed to the still-open sase-zr.7.1.1.3 for owner_conflict to wire up and clear. Full detail in the preceding notes.

## Dependencies

- **Depends on:** [sase-zr.7.1.1.1](sase-zr.7.1.1.1.md) ✓ · ⧖ 2026-09-17
- **Blocks:** [sase-zr.7.1.1.3](sase-zr.7.1.1.3.md) ◐ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-zr.7.1.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-zr.7.1.1.2/README.md) | [sase-zr.7.1.1.2](sase-zr.7.1.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`934be03`](https://github.com/sase-org/sase/commit/934be032dd7ea5fa61f5017fb90aeaac8d87c760) | feat(gate-decision): journal acceptance ids and durable attempt-failure outcomes | [sase-zr.7.1.1.2](sase-zr.7.1.1.2.md) | 2026-09-17 13:59:23 EDT |
