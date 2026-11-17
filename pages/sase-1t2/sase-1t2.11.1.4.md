# Bead: sase-1t2.11.1.4 — Enable running and settling monitor hijacks

[Bead Pages](../README.md) / [sase-1t2.11.1](sase-1t2.11.1.md) / sase-1t2.11.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t2.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.11.md) · **Assignee:** `sase-1t2.11.1.4` · **Size:** medium
**Created:** 2026-11-16 15:27:13 EST · **Closed:** 2026-11-17 00:03:29 EST
**Plan:** [202611/monitor\_hijack\_adapter.md](https://github.com/sase-org/sase--plans/blob/main/202611/monitor_hijack_adapter.md)

## Description

activation: gather durable monitor occupancy and pending-follow-up facts, enable Rust immediate/monitor and latched/monitor decisions with their mechanisms, and prove request-versus-settlement races preserve custody and launch at most one successor.

## Notes

[2026-11-17T05:03:10Z · sase-1t2.11.1.4] PROPOSED FOLLOW-UP: just check dca916f4d5f596dc5078824cc34e6519 verdict no_new_failures — KNOWN tests/continuation/test_launch_local_capture_chain.py::test_twenty_launch_agent_monitor_cycles_keep_only_local_authored_text (witness 2de29a5875d9b3cd2cefe798a2363544, also noted on sase-1t2.11.1.1 / sase-1t3.6.1) and FLAKY tests/fakey/test_provider_drain_e2e.py::test_provider_drain_e2e_relaunches_stranded_agent (sase-1k2).

[2026-11-17T05:03:29Z · sase-1t2.11.1.4] Enabled public running/settling monitor hijacks: Rust v2 facts add monitor_followup_pending; occupying MONITOR decides immediate adapter=monitor (no LLM/PID); pending follow-up latches boundary=monitor before already_completed; delivered/unclaimed refuse. Python facts require frozen continue+command settled (not mere monitor_next_action). Latch request allows monitors (lane then target_index); terminal monitors settle via settle_monitor_hijack; resume refuses hijack_pending. Nested log_file_lock is reentrant so start-teardown settlement does not deadlock on a second lane fd. Verified: just rust-install; focused pytest 52+7 (including previously hung start-ack/teardown); sase-core check 9f29a9e64bcbc6d53a86828bad829143; sase check dca916f4d5f596dc5078824cc34e6519 no_new_failures (1 KNOWN + 1 FLAKY recorded as PROPOSED FOLLOW-UP). No epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1t2.11.1.3](sase-1t2.11.1.3.md) ✓ · ⧖ 2026-11-16
- **Blocks:** [sase-1t2.11.1.6](sase-1t2.11.1.6.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t2.11.1.7](sase-1t2.11.1.7.md) ◐ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.11.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.11.1.4/README.md) | [sase-1t2.11.1.4](sase-1t2.11.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@aef1da8`](https://github.com/sase-org/sase-core/commit/aef1da8b05f7b60c32c74ce06dd91ae4a5983085) | feat(agent-hijack): decide running and latched monitor occupancy | [sase-1t2.11.1.4](sase-1t2.11.1.4.md) | 2026-11-17 00:05:12 EST |
