# Bead: sase-ng.1.4 — Retire the in-process launch body and fan-out dispatchers

[Bead Pages](../README.md) / [sase-ng.1](sase-ng.1.md) / sase-ng.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ng](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ng.md) · **Assignee:** `sase-ng.1.4` · **Size:** medium
**Created:** 2026-08-17 15:16:51 EDT · **Closed:** 2026-08-17 17:04:01 EDT
**Plan:** [202608/retire\_dead\_ace\_launch\_cleanup\_bodies.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_dead_ace_launch_cleanup_bodies.md)

## Description

launch_retire: delete `run_agent_launch_body`, `run_single_agent_launch_body`, the four fan-out dispatcher mixins, and `proc_callable` on `_submit_launch_proc`, then delete or re-point every test that reached them through the discarded callable.

## Notes

[2026-08-17T21:04:01Z · sase-ng.1.4] Deleted the in-process launch body and fan-out dispatchers and re-pointed tests at the durable submit seam.

Source: removed `_launch_body.py`, `_launch_body_impl.py`, `_launch_body_single.py`, `_launch_bulk.py`, `_launch_multi_prompt.py`, `_launch_multi_model.py`, `_launch_repeat.py`. Dropped those mixins from `AgentLaunchMixin`. Removed `proc_callable` from `_submit_launch_proc` and the last production pass in `_launch_resolved_prompt`. Privatized `_LaunchProcOutcome` / `_launch_results_tuple` and deleted unused `with_warning_messages` (tests now assert on the dict result payload).

Tests deleted (subject was the discarded callable): `test_agent_launch_dispatch.py`, `test_launch_repeat_bulk.py`, `test_launch_multi_prompt.py`, `test_launch_multi_model.py`, `test_prompt_stack_launch_integration.py`, `test_agent_launch_repeat.py`, `agent_launch_vcs/` (except `resolve_ref_from_prompt`, moved to `tests/ace/tui/test_resolve_ref_from_prompt.py`). Trimmed helpers and re-pointed `test_prompt_bar_stack_submit_handlers.py` / `test_prompt_input_collection_launch.py` at recorded `prompt` / `extra_payload`. Durable replacements: `launch_cwd_agents` / `multi_prompt_launcher` / `repeat_launcher` tests; ACE toast coverage stays in `test_agent_launch_non_blocking.py`.

Force-reuse tests removed from `test_agent_launch_non_blocking.py` only after confirming replacements: family wipe → `test_plan_collects_family_member_owner_name` + `test_launch_query_consumes_authorized_family_form`; segment bead markers → `test_plan_threads_per_segment_owner_names_and_envs` + `test_launch_query_threads_multi_prompt_segment_envs`; multi-prompt wipe → those plus `test_apply_wipes_planned_owner_names`; fenced separator → `test_plan_ignores_separator_inside_fenced_block`; early parse / reserved `--` / wipe failure → `test_plan_early_parse_failure_does_not_reach_apply`, `test_plan_rejects_reserved_family_separator_before_wipe`, `test_launch_query_parse_failure_records_and_emits`, `test_launch_query_wipe_failure_records_and_emits`. Kept `test_finish_agent_launch_force_reuse_submits_raw_prompt_unrewritten`.

Second-order orphans left for sase-ng.1.5 (`--epic-symbol`): `_launch_history` recorders, `strip_all_vcs_refs`, `strip_known_project_vcs_refs`.

Verified: `just install`; targeted launch/submit tests; `just _lint-symvision`; `just check` (lint + scoped lane escalated to the governed full suite and passed).

[2026-08-17T21:05:06Z · sase-ng.1.4] Deleted in-process launch body/fan-out dispatchers and proc_callable; re-pointed tests at durable sase run path. Verified: just install, targeted launch/submit tests, just _lint-symvision, just check (scoped lane escalated to full suite and passed). No leftover --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-ng.1.1](sase-ng.1.1.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-ng.1.2](sase-ng.1.2.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-ng.1.5](sase-ng.1.5.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ng.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ng.1.4/README.md) | [sase-ng.1.4](sase-ng.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0f7d86a`](https://github.com/sase-org/sase/commit/0f7d86a662c4c6e66bedbe248079f96f991adf89) | refactor(tui): retire in-process launch body and fan-out dispatchers | [sase-ng.1.4](sase-ng.1.4.md) | 2026-08-17 17:06:32 EDT |
