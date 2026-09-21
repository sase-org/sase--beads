# Bead: sase-157.4 — Gate the procfs process-identity token to Linux

[Bead Pages](../README.md) / [sase-157](README.md) / sase-157.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oj.md) · **Assignee:** `sase-157.4` · **Size:** medium
**Created:** 2026-09-21 06:25:47 EDT
**Plan:** [202609/macos\_portability.md](https://github.com/sase-org/sase--plans/blob/main/202609/macos_portability.md)

## Description

sudo-identity: split process_identity_token so the procfs body is target_os = linux with an explicit unsupported-platform error elsewhere, add a config test seam so the detached handshake tests keep running off Linux, and make the macOS story for the sase_sudo_runner console script explicit.

## Dependencies

- **Depends on:** [sase-157.3](sase-157.3.md) ◐ · ⧖ 2026-09-21
- **Blocks:** [sase-157.5](sase-157.5.md) ◐ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-157.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.4/README.md) | [sase-157.4](sase-157.4.md) | 0 |
