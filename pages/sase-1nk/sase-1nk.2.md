# Bead: sase-1nk.2 — Restore the host PATH for agent launches made from agent shells

[Bead Pages](../README.md) / [sase-1nk](README.md) / sase-1nk.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.133](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.133.md) · **Assignee:** `sase-1nk.2` · **Size:** medium
**Created:** 2026-10-23 09:29:10 EDT
**Plan:** [202610/monitor\_followup\_output\_and\_host\_path.md](https://github.com/sase-org/sase--plans/blob/main/202610/monitor_followup_output_and_host_path.md)

## Description

host-path-launch-env: runners stamp a SASE_HOST_PATH_SNAPSHOT of their PATH and spawn_agent_subprocess restores it, so login-shell PATH resets cannot hide provider CLIs.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nk.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nk.2/README.md) | [sase-1nk.2](sase-1nk.2.md) | 0 |
