# Bead: sase-mc.4 — Document, stress, and land the combined provider-disable feature

[Bead Pages](../README.md) / [sase-mc](README.md) / sase-mc.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02f](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02f.md) · **Assignee:** `sase-mc.4` · **Size:** small
**Created:** 2026-08-15 11:12:22 EDT · **Closed:** 2026-08-15 15:39:02 EDT
**Plan:** [202608/temporary\_provider\_disabling.md](https://github.com/sase-org/sase--plans/blob/main/202608/temporary_provider_disabling.md)

## Description

integration-and-docs: reconcile cross-phase behavior, update the LLM/ACE/Rust-backend docs, run the full sase-core and sase verification lanes including visual snapshots, and exercise expiry, fallback, direct-request, and multi-process state transitions in an end-to-end smoke matrix before landing.

## Notes

[2026-08-15T19:04:56Z · sase-mc.4] PROPOSED FOLLOW-UP: Fix unrelated ACE visual snapshot suite failures — `just test-visual` currently errors in commits visual fixtures because `sase.ace.tui.widgets.artifacts.commits_filtering.normalize_reference_time` is missing, and several non-provider artifact/agent PNG goldens mismatch.

[2026-08-15T19:38:05Z · sase-mc.4] PROPOSED FOLLOW-UP: Fix phase-agent monitor startup failure — `sase monitor start` from agent `sase-mc.4` fails before launching with `Cannot create agent family 'sase-mc': resolved parent is named 'sase-mc.4'`, and `sase monitor list --all` reports a non-monitor artifact record.

[2026-08-15T19:38:26Z · sase-mc.4] PROPOSED FOLLOW-UP: Update reproducible-flake baseline or fix unrelated flakes — `just selection-health --fail-on-new-flake` currently reports four new reproducible flakes (`tests/monitor/test_monitor_supervise.py::test_run_supervisor_times_out_after_partial_line`, `tests/notification_store/test_mute_snooze.py::TestMarkSnoozed::test_round_trip`, `tests/test_plan_approval_actions.py::test_headless_epic_approval_submits_while_inflight_launch_holds_anchor`, `tests/test_procs_service.py::test_settlement_resumes_after_an_injected_crash`) plus one stale deleted-node baseline entry.

[2026-08-15T19:39:02Z · sase-mc.4] Verified provider-disable docs and smoke matrix; linked core just check passed; main just check passed and escalated to full non-visual suite; focused provider-disable routing/smoke/unit tests passed; provider-disable visual subset passed. Full visual suite has unrelated failures recorded as PROPOSED FOLLOW-UP. Monitor check-full startup failed and selection-health has unrelated flake baseline failures, both recorded as PROPOSED FOLLOW-UP.

[2026-08-15T19:39:53Z · sase-mc.4] Verified linked sase-core just check passed; main repo just check passed with full non-visual suite escalation; provider-disable smoke/routing/unit tests passed; provider-disable visual subset passed. Recorded unrelated visual, monitor, and flake-baseline caveats as proposed follow-ups.

## Dependencies

- **Depends on:** [sase-mc.3](sase-mc.3.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mc.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mc.4/README.md) | [sase-mc.4](sase-mc.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3a31bd3`](https://github.com/sase-org/sase/commit/3a31bd3b8c4a5082edc772b50f07103436ff5764) | feat(llm): land provider disable integration | [sase-mc.4](sase-mc.4.md) | 2026-08-15 15:42:51 EDT |
