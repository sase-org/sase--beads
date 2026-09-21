# Bead: sase-11y.10.1.7.1 — Route the chat-install post-update recovery through the service host

[Bead Pages](../README.md) / [sase-11y.10.1.7](sase-11y.10.1.7.md) / sase-11y.10.1.7.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.land.md) · **Assignee:** `sase-11y.10.1.7.1` · **Size:** medium
**Created:** 2026-09-21 03:59:13 EDT
**Plan:** [202609/service\_host\_sunset\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset_finish.md)

## Description

chat-restart: make the chat-install update worker bring the scheduler back through the `scheduler` service proc instead of `start_axe_daemon`, retitle its messages to "scheduler", and delete `start_axe_daemon` plus every `_process_start.py` helper that loses its last caller (sase-152).

## Dependencies

- **Blocks:** [sase-11y.10.1.7.2](sase-11y.10.1.7.2.md) ◐ · ⧖ 2026-09-21
- **Blocks:** [sase-11y.10.1.7.5](sase-11y.10.1.7.5.md) ◐ · ⧖ 2026-09-21
- **Blocks:** [sase-11y.10.1.7.6](sase-11y.10.1.7.6.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.7.1/README.md) | [sase-11y.10.1.7.1](sase-11y.10.1.7.1.md) | 0 |
