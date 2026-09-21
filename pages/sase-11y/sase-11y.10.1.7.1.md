# Bead: sase-11y.10.1.7.1 — Route the chat-install post-update recovery through the service host

[Bead Pages](../README.md) / [sase-11y.10.1.7](sase-11y.10.1.7.md) / sase-11y.10.1.7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.land.md) · **Assignee:** `sase-11y.10.1.7.1` · **Size:** medium
**Created:** 2026-09-21 03:59:13 EDT · **Closed:** 2026-09-21 04:23:00 EDT
**Plan:** [202609/service\_host\_sunset\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset_finish.md)

## Description

chat-restart: make the chat-install update worker bring the scheduler back through the `scheduler` service proc instead of `start_axe_daemon`, retitle its messages to "scheduler", and delete `start_axe_daemon` plus every `_process_start.py` helper that loses its last caller (sase-152).

## Notes

[2026-09-21T08:23:00Z · sase-11y.10.1.7.1] chat-install recovery now goes through start_service_proc('scheduler', actor='chat-install') + start_service_host when down, polling persisted_or_current_status() up to restart_attempts times (kept as poll budget, docs retitled to scheduler); exit 5 kept; verified sase-telegram renders the completion message generically. Deleted restart_axe worker helper, start_axe_daemon/start_axe_daemon_result and all orphaned _process_start helpers (kept canonical_axe_start_command for service/executable.py), AxeStartResult/StartStatus, get_pid_from_pid_files, notify_axe_lock_recovered; made _AxeLifecycleLock and _terminate_process private with test updates; deleted tests/test_axe_process_start.py. Verified: 27 chat/guard/journal tests + 3 outage regressions + 42 lock/stop/orchestrator/service-status tests pass; sase tool run check green except the two known sase-14j symvision reports left per plan; no epic-symbols left.

## Dependencies

- **Blocks:** [sase-11y.10.1.7.2](sase-11y.10.1.7.2.md) ◐ · ⧖ 2026-09-21
- **Blocks:** [sase-11y.10.1.7.5](sase-11y.10.1.7.5.md) ◐ · ⧖ 2026-09-21
- **Blocks:** [sase-11y.10.1.7.6](sase-11y.10.1.7.6.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.7.1/README.md) | [sase-11y.10.1.7.1](sase-11y.10.1.7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`62c902f`](https://github.com/sase-org/sase/commit/62c902f0deccaead6b32de6a88fef9bc83e37aa5) | feat(chat-restart): route chat-install recovery through scheduler service host | [sase-11y.10.1.7.1](sase-11y.10.1.7.1.md) | 2026-09-21 04:25:43 EDT |
