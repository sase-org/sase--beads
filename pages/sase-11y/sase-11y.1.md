# Bead: sase-11y.1 — Cgroup escape helper for detached work

[Bead Pages](../README.md) / [sase-11y](README.md) / sase-11y.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0m3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0m3.md) · **Assignee:** `sase-11y.1` · **Size:** medium
**Created:** 2026-09-16 14:41:57 EDT
**Plan:** [202609/service\_host\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_1.md)

## Description

detach-scope: add a detach_scope helper that lets agents, detached procs, monitors/gates, and gateway bridges escape the service unit's cgroup (systemd-run scope on Linux, setsid on macOS), apply it at every detach point, and rename src/sase/procs/service.py.

## Dependencies

- **Blocks:** [sase-11y.4](sase-11y.4.md) ◐ · ⧖ 2026-09-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.1/README.md) | [sase-11y.1](sase-11y.1.md) | 0 |
