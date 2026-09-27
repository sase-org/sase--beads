# Bead: sase-1bf.2 — Rust-owned launch scratch liveness that works under systemd

[Bead Pages](../README.md) / [sase-1bf](README.md) / sase-1bf.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.1d` · **Assignee:** `sase-1bf.2` · **Size:** medium
**Created:** 2026-09-27 14:23:32 EDT
**Plan:** [202609/bounded\_agent\_scratch.md](https://github.com/sase-org/sase--plans/blob/main/202609/bounded_agent_scratch.md)

## Description

scratch-liveness: move the procfs liveness probe into sase-core, stop treating pre-launch non-dumpable processes (systemd --user, sd-pam, ssh-agent) as incomplete observations, and make runner-exit cleanup log every outcome.

## Dependencies

- **Blocks:** [sase-1bf.3](sase-1bf.3.md) ◐ · ⧖ 2026-09-27
- **Blocks:** [sase-1bf.6](sase-1bf.6.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bf.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bf.2/README.md) | [sase-1bf.2](sase-1bf.2.md) | 0 |
