# Bead: sase-11y.1 — Cgroup escape helper for detached work

[Bead Pages](../README.md) / [sase-11y](README.md) / sase-11y.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0m3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0m3.md) · **Assignee:** `sase-11y.1` · **Size:** medium
**Created:** 2026-09-16 14:41:57 EDT · **Closed:** 2026-09-16 17:34:10 EDT
**Plan:** [202609/service\_host\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_1.md)

## Description

detach-scope: add a detach_scope helper that lets agents, detached procs, monitors/gates, and gateway bridges escape the service unit's cgroup (systemd-run scope on Linux, setsid on macOS), apply it at every detach point, and rename src/sase/procs/service.py.

## Notes

[2026-09-16T21:33:45Z · sase-11y.1] PROPOSED FOLLOW-UP: Implement %hold prompt directive parsing in the Python runtime — linked sase-core now advertises %hold under agent_holds; this phase only classified it as a special contract row so current checks stay aligned while the actual directive behavior is triaged separately.

[2026-09-16T21:34:10Z · sase-11y.1] Implemented detach_scope and wired proc, monitor, agent, admission, gate/proc, and gateway-agent launch paths; renamed proc submission module; added pipe-safe pid-file handoff for systemd-run bootstrap launches; verified focused pytest (76 passed, 1 skipped), just fix, just check (full-suite escalation green), and epic-symbols clean.

## Dependencies

- **Blocks:** [sase-11y.4](sase-11y.4.md) ◐ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.1/README.md) | [sase-11y.1](sase-11y.1.md) | 0 |
