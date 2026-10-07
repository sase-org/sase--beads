# Bead: sase-1h9.4 — No terminal wait alert for superseded session members

[Bead Pages](../README.md) / [sase-1h9](README.md) / sase-1h9.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0xo](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0xo.md) · **Assignee:** `sase-1h9.4` · **Size:** small
**Created:** 2026-10-07 07:52:37 EDT
**Plan:** [202610/finalizer\_repair\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/202610/finalizer_repair_hardening.md)

## Description

wait-terminal-alerts: limit wait_checks terminal-blocker detection to members that are really terminal, so a failed monitor whose follow-up turn launched (or any member superseded by a newer one) no longer raises a false "Wait dependency can never self-resolve" notification.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h9.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h9.4/README.md) | [sase-1h9.4](sase-1h9.4.md) | 0 |
