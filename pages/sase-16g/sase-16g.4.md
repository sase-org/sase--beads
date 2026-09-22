# Bead: sase-16g.4 — The host honors give\_up and says so

[Bead Pages](../README.md) / [sase-16g](README.md) / sase-16g.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pe](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pe.md) · **Assignee:** `sase-16g.4` · **Size:** medium
**Created:** 2026-09-22 12:59:11 EDT · **Closed:** 2026-09-22 15:35:22 EDT
**Plan:** [202609/services\_p0\_supervision.md](https://github.com/sase-org/sase--plans/blob/main/202609/services_p0_supervision.md)

## Description

giveup: stop relaunching procs the restart policy gave up on, keep a signature-keyed given-up record that an explicit request clears, emit a durable notification on crash-loop and on give-up while desired running, and make the Telegram receiver exit retryable instead of reporting missing credentials as success.

## Notes

[2026-09-22T19:34:20Z · sase-16g.4] PROPOSED FOLLOW-UP: symvision fails at baseline on agent_env_refusal_reason in src/sase/service/platform.py (env-phase scope, fails on clean tree without giveup changes)

[2026-09-22T19:34:48Z · sase-16g.4] PROPOSED FOLLOW-UP: sase-telegram has pre-existing failures on clean tree — test_telegram_submits_a_shell_backed_gate (gate-shell GateError) and two test_receiver_runtime.py order-dependent mtime flakes

[2026-09-22T19:35:22Z · sase-16g.4] give_up honored: host parks give_up procs (signature-keyed, stop-requested excluded, spawn failures included), loop-3 skips parked entries, explicit requests and signature changes revive, snapshot emits exited with last exit, crash-loop/give-up upsert one service notification per episode with revive command; telegram receiver returns 75 on missing bot token (0 stays for disabled, 78 for chat-id). Verified: 24/24 host-scenario tests (7 new), 194/194 tests/service, telegram lint+43 touched tests green; just check symvision red only on pre-existing agent_env_refusal_reason (fails at baseline, env scope, follow-up noted); epic-symbols clean

## Dependencies

- **Depends on:** [sase-16g.3](sase-16g.3.md) ✓ · ⧖ 2026-09-22
- **Blocks:** [sase-16g.5](sase-16g.5.md) ◐ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16g.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16g.4/README.md) | [sase-16g.4](sase-16g.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`716c77d`](https://github.com/sase-org/sase/commit/716c77dce324cb2ef6f36990efaf8a0a416c397b) | feat(service): honor give\_up with parked records and loud failure notifications | [sase-16g.4](sase-16g.4.md) | 2026-09-22 15:37:16 EDT |
