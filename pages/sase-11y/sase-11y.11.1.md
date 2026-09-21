# Bead: sase-11y.11.1 — Escape the service cgroup at the remaining detached runner spawns

[Bead Pages](../README.md) / [sase-11y.11](sase-11y.11.md) / sase-11y.11.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.land.md) · **Assignee:** `sase-11y.11.1` · **Size:** medium
**Created:** 2026-09-21 07:19:29 EDT · **Closed:** 2026-09-21 08:04:43 EDT
**Plan:** [202609/service\_host\_landing\_leftovers.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_landing_leftovers.md)

## Description

detach-runners: route the CRS, fix-hook, and summarize workflow runners, the mentor runner, the checks runner, hook execution, and the chat-install update worker through `detach_scope`, so that a `sase.service` stop or restart (`KillMode=mixed`) no longer SIGKILLs them. Prove that recorded PIDs and the chat-install lock fd survive the wrap.

## Notes

[2026-09-21T12:03:53Z · sase-11y.11.1] PROPOSED FOLLOW-UP: just check stays red on sase-14j symvision findings (bead_touch_glyph, ordered_bead_verb_chips in _agent_bead_touches.py), untouched by this phase — needs sase-14j or epic-symbols phase to resolve

[2026-09-21T12:04:43Z · sase-11y.11.1] Wrapped all 7 runner spawns (CRS, fix-hook, summarize, mentor, checks, hook execution, chat-install worker) through detach_scope with distinct sase-<kind> unit prefixes; Popen now uses launch.argv and launch.start_new_session so a sase.service stop/restart no longer SIGKILLs them and TUI-launched noop behavior is unchanged. Verified: 14 new unit tests (escaped+noop per site) plus 2 gated live tests for PID-unchanged and lock-fd survival in tests/test_detach_scope.py — 31 passed/3 skipped (live skips outside SASE unit); existing suites pass (chat_install+checks_runner 51 passed, timezone 22 passed); just fix clean; just check green except pre-existing sase-14j symvision findings in untouched _agent_bead_touches.py (noted as PROPOSED FOLLOW-UP). Lock-fd survival through systemd-run --scope also proven manually in this environment.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.11.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.11.1/README.md) | [sase-11y.11.1](sase-11y.11.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`213c481`](https://github.com/sase-org/sase/commit/213c481363af70deba92ee0c0dc3ee8e0c97b37c) | feat(scheduler): escape detached runners from the service cgroup via detach\_scope | [sase-11y.11.1](sase-11y.11.1.md) | 2026-09-21 08:06:31 EDT |
