# Bead: sase-1qn.5 — Fix the AGY usage-probe rate-limit timeout flake (sase-19m)

[Bead Pages](../README.md) / [sase-1qn](README.md) / sase-1qn.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pu.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pu.land.md) · **Assignee:** `sase-1qn.5` · **Size:** medium
**Created:** 2026-11-01 14:34:49 EST · **Closed:** 2026-11-01 16:41:02 EST
**Plan:** [202611/task\_backlog\_epic\_4.md](https://github.com/sase-org/sase--plans/blob/main/202611/task_backlog_epic_4.md)

## Description

agy-probe-timeout-flake: tests/llm_provider/test_agy_usage_probe.py::test_agy_usage_probe_timeout_with_rate_limit_stderr_is_rate_limited fails under the loaded diff-scoped lane (timeout classified instead of rate_limited; latest +1 2026-11-01) and passes alone. Make the test and, if needed, the probe classification deterministic under load while keeping the rate-limit-wins-over-timeout contract.

## Notes

[2026-11-01T21:40:38Z · sase-1qn.5] TASK RESOLVED: sase-19m — _wait_for_usage now drains stderr already in the pipe before and after kill, so rate-limit text written before the deadline classifies as rate_limited; timeout without that evidence stays timeout. The isolate wrapper keeps a completed worker observation when the outer deadline races the last stdout read. test_agy_usage_probe_timeout_with_rate_limit_stderr_is_rate_limited uses a ready-file sync (expired deadline after stderr flush) plus collect classification; 20/20 serial, 55 xdist probe tests, node 0.12s.

[2026-11-01T21:40:44Z · sase-1qn.5] PROPOSED FOLLOW-UP: scoped check ToolRun 4062c1f3bb6b5a9d84097982381aef9f failed unrelated parallel-lane nodes. bead_claim_checks empty holders / missing tombstone matches sase-1oo; dismiss leftover keys matches sase-1pr; group revive extra agents matches sase-1on. Those nodes passed serially on this tree.

[2026-11-01T21:40:50Z · sase-1qn.5] PROPOSED FOLLOW-UP: test_pending_actions.py::test_transport_adapter_preserves_handled_state_and_original_lifecycle KeyError abcd1234 after remove_transport_action reproduces identically on clean master (stashed worktree) and with this phase diff; no existing task bead found.

[2026-11-01T21:40:55Z · sase-1qn.5] PROPOSED FOLLOW-UP: test_stranded_work_facade.py::test_reduce_stranded_work_round_trips_through_real_binding asserts schema_version 1 but the linked sase-core binding returns 2; same failure on clean master. Matches the check-run core-floor-probe that sase-core is ahead of sase-core-rs==0.43.2.

[2026-11-01T21:41:02Z · sase-1qn.5] Verified sase-19m: rate-limit stderr captured before timeout yields rate_limited (ready-file sync + collect classification); timeout without that stderr stays timeout. Isolate wrapper prefers a completed worker observation over outer timeout. 20/20 serial on the flake node, 55 xdist probe tests. Unrelated scoped-lane failures reproduced on clean master or match sase-1oo/sase-1pr/sase-1on; recorded as PROPOSED FOLLOW-UP. No --epic-symbol leftovers.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1qn.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1qn.5/README.md) | [sase-1qn.5](sase-1qn.5.md) | 0 |
