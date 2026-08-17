# Bead: sase-ng.1.1 — Restore forced name reuse on the durable launch path

[Bead Pages](../README.md) / [sase-ng.1](sase-ng.1.md) / sase-ng.1.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ng](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ng.md) · **Assignee:** `sase-ng.1.1` · **Size:** medium
**Created:** 2026-08-17 15:16:50 EDT
**Plan:** [202608/retire\_dead\_ace\_launch\_cleanup\_bodies.md](https://github.com/sase-org/sase--plans/blob/main/202608/retire_dead_ace_launch_cleanup_bodies.md)

## Description

force_reuse: extract the `%id:!name` force-reuse launch pipeline out of the orphaned TUI body into a shared `sase.agent.force_reuse_launch` module, carry ACE's confirmation through the `RUN_LAUNCH` request payload, and consume it in the `sase run` child so kill-and-edit relaunches work again before the orphaned copy is deleted.

## Notes

[2026-08-17T19:46:38Z · sase-ng.1.1] PROGRESS: Shared force-reuse pipeline was already on master (dc4ca2057). This phase kept run_agent_launch_body pointed at that helper, widened launch_query planning failures to emit a typed result, and added durable-path seam tests from prepare_kill_and_edit_prompt through RUN_LAUNCH into launch_query (clan/family, multi-prompt segment envs, fan-out/parse/wipe failures, alias --- segmentation, unauthorized sidecar). just check lint passed; scoped tests escalated (core-identity-changed). Handing just check-full to a monitor before close.

[2026-08-17T19:53:53Z · sase-ng.1.1--1] PROPOSED FOLLOW-UP: sase-oc.8 closed leaving Justfile --epic-symbol sase-oc.8(set_completion_summary) stale — re-keyed to still-open parent sase-oc. set_completion_summary still has no production caller on this tree (only tests); sase-oc.land must land the polish overrides from the cli_completion plan or delete the unused public setter and drop the whitelist.

## Dependencies

- **Blocks:** [sase-ng.1.4](sase-ng.1.4.md) ◐ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ng.1.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ng.1.1.md) | [sase-ng.1.1](sase-ng.1.1.md) | 0 |
