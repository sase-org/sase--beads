# Bead: sase-ng.1.1 — Restore forced name reuse on the durable launch path

[Bead Pages](../README.md) / [sase-ng.1](sase-ng.1.md) / sase-ng.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ng](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ng.md) · **Assignee:** `sase-ng.1.1` · **Size:** medium
**Created:** 2026-08-17 15:16:50 EDT · **Closed:** 2026-08-17 16:16:39 EDT
**Plan:** [202608/retire\_dead\_ace\_launch\_cleanup\_bodies.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_dead_ace_launch_cleanup_bodies.md)

## Description

force_reuse: extract the `%id:!name` force-reuse launch pipeline out of the orphaned TUI body into a shared `sase.agent.force_reuse_launch` module, carry ACE's confirmation through the `RUN_LAUNCH` request payload, and consume it in the `sase run` child so kill-and-edit relaunches work again before the orphaned copy is deleted.

## Notes

[2026-08-17T19:46:38Z · sase-ng.1.1] PROGRESS: Shared force-reuse pipeline was already on master (dc4ca2057). This phase kept run_agent_launch_body pointed at that helper, widened launch_query planning failures to emit a typed result, and added durable-path seam tests from prepare_kill_and_edit_prompt through RUN_LAUNCH into launch_query (clan/family, multi-prompt segment envs, fan-out/parse/wipe failures, alias --- segmentation, unauthorized sidecar). just check lint passed; scoped tests escalated (core-identity-changed). Handing just check-full to a monitor before close.

[2026-08-17T19:53:53Z · sase-ng.1.1--1] PROPOSED FOLLOW-UP: sase-oc.8 closed leaving Justfile --epic-symbol sase-oc.8(set_completion_summary) stale — re-keyed to still-open parent sase-oc. set_completion_summary still has no production caller on this tree (only tests); sase-oc.land must land the polish overrides from the cli_completion plan or delete the unused public setter and drop the whitelist.

[2026-08-17T20:16:39Z · sase-ng.1.1--1] Verified forced name reuse on the durable path: plan_force_reuse_launch/apply_force_reuse_launch, ACE RUN_LAUNCH allow_force_reuse, launch_query plan/wipe/rewritten prompt/segment_extra_env, first-slot-only SASE_AGENT_FORCE_REUSE_BEAD, fan-out contradiction explicit error, unauthorized sase run still rejected. run_agent_launch_body re-pointed at the shared helper (not deleted). Durable-path replacements for the seven test_agent_launch_non_blocking proc_callable force-reuse cases: submits_raw_prompt -> seam submission tests; family attach wipe -> test_launch_query_consumes_authorized_family_form + test_plan_collects_family_member_owner_name; segment bead markers / wipe every name -> test_launch_query_threads_multi_prompt_segment_envs + test_plan_threads_per_segment_owner_names_and_envs; fenced separator -> test_plan_ignores_separator_inside_fenced_block; early parse no wipe -> test_plan_early_parse_failure_does_not_reach_apply + test_launch_query_parse_failure_records_and_emits; invalid family -- -> test_plan_rejects_reserved_family_separator_before_wipe; wipe failure -> test_launch_query_wipe_failure_records_and_emits. launch_retire can delete the leftover proc_callable copies. Unblocked just check by re-keying stale --epic-symbol sase-oc.8(set_completion_summary) to still-open parent sase-oc (sase-oc.8 closed leaving the unused public setter). sase bead epic-symbols sase-ng.1.1 reports no leftovers. just check passed after scoped escalation to the full suite (rules: justfile).

[2026-08-17T20:18:46Z · sase-ng.1.1--1] Verified forced name reuse on the durable path: plan_force_reuse_launch/apply_force_reuse_launch, ACE RUN_LAUNCH allow_force_reuse, launch_query plan/wipe/rewritten prompt/segment_extra_env, first-slot-only SASE_AGENT_FORCE_REUSE_BEAD, fan-out contradiction explicit error, unauthorized sase run still rejected. run_agent_launch_body re-pointed at the shared helper (not deleted). Durable-path replacements for the seven test_agent_launch_non_blocking proc_callable force-reuse cases: submits_raw_prompt -> seam submission tests; family attach wipe -> test_launch_query_consumes_authorized_family_form + test_plan_collects_family_member_owner_name; segment bead markers / wipe every name -> test_launch_query_threads_multi_prompt_segment_envs + test_plan_threads_per_segment_owner_names_and_envs; fenced separator -> test_plan_ignores_separator_inside_fenced_block; early parse no wipe -> test_plan_early_parse_failure_does_not_reach_apply + test_launch_query_parse_failure_records_and_emits; invalid family -- -> test_plan_rejects_reserved_family_separator_before_wipe; wipe failure -> test_launch_query_wipe_failure_records_and_emits. launch_retire can delete the leftover proc_callable copies. Unblocked just check by re-keying stale --epic-symbol sase-oc.8(set_completion_summary) to still-open parent sase-oc (sase-oc.8 closed leaving the unused public setter). sase bead epic-symbols sase-ng.1.1 reports no leftovers. just check passed after scoped escalation to the full suite (rules: justfile).

## Dependencies

- **Blocks:** [sase-ng.1.4](sase-ng.1.4.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ng.1.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ng.1.1.md) | [sase-ng.1.1](sase-ng.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`13e9ccb`](https://github.com/sase-org/sase/commit/13e9ccbc9b1b044fe1a56f8d3c505f65af235352) | fix(agent): consume force-reuse plans on the durable launch path | [sase-ng.1.1](sase-ng.1.1.md) | 2026-08-17 16:21:41 EDT |
