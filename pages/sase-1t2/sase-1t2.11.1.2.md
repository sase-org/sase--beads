# Bead: sase-1t2.11.1.2 — Recover the recorded monitor follow-up

[Bead Pages](../README.md) / [sase-1t2.11.1](sase-1t2.11.1.md) / sase-1t2.11.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t2.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.11.md) · **Assignee:** `sase-1t2.11.1.2` · **Size:** medium
**Created:** 2026-11-16 15:27:12 EST · **Closed:** 2026-11-16 19:16:25 EST
**Plan:** [202611/monitor\_hijack\_adapter.md](https://github.com/sase-org/sase--plans/blob/main/202611/monitor_hijack_adapter.md)

## Description

followup: implement monitor-scope Continue and Escalate through exactly-once recovery admission with bounded untrusted partial output; provide truthful Rust recovery rows and preserve the same workspace.

## Notes

[2026-11-17T00:15:56Z · sase-1t2.11.1.2] PROPOSED FOLLOW-UP: TUI import budget already exceeds the 12,162,484 cap on merge-base a2c9c3ec (12,311,609 bytes); this phase deferred sase.agent.hijack._preview_monitor from TUI startup so the remaining delta is existing hijack modules only

[2026-11-17T00:16:03Z · sase-1t2.11.1.2] PROPOSED FOLLOW-UP: just check scoped lane reported FLAKY/NEW fakey drain e2e (test_provider_drain_e2e_relaunches_stranded_agent) and FLAKY continuation capture (test_twenty_launch_agent_monitor_cycles_keep_only_local_authored_text); neither is monitor keep-work recovery

[2026-11-17T00:16:09Z · sase-1t2.11.1.2] PROPOSED FOLLOW-UP: KNOWN fakey hijack canary test_finalizing_latch_suppresses_staged_pipe_then_continues_same_workspace refuses with unnumbered_workspace (witness 0297c0b9e7f93a8615f576f01f20e711)

[2026-11-17T00:16:25Z · sase-1t2.11.1.2] Monitor keep-work recovery: Rust truthful rows (Continue/Escalate/View/Shell/Dismiss, rerun unavailable), Python descriptor/prompt/same-workspace adapters, frozen-intent model pin, untrusted bounded output. Verified sase-core just check (92bea3a09e8e80af548ad604c0f8c726), sase_core preview+py hijack tests, tests/test_agent_hijack_monitor_followup.py, recover_target, marker-path review. Scoped just check lint green; leftover NEW/KNOWN/FLAKY recorded as follow-ups. No leftover --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-1t2.11.1.1](sase-1t2.11.1.1.md) ✓ · ⧖ 2026-11-16
- **Blocks:** [sase-1t2.11.1.3](sase-1t2.11.1.3.md) ◐ · ⧖ 2026-11-16
- **Blocks:** [sase-1t2.11.1.7](sase-1t2.11.1.7.md) ◐ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.11.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.11.1.2/README.md) | [sase-1t2.11.1.2](sase-1t2.11.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@2108ed3`](https://github.com/sase-org/sase-core/commit/2108ed33bb8301e2b2b14e16bcc6a35a8586be76) | feat(agent-hijack): add monitor-scope recovery preview rows | [sase-1t2.11.1.2](sase-1t2.11.1.2.md) | 2026-11-16 19:17:47 EST |
