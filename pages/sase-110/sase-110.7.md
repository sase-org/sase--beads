# Bead: sase-110.7 — Chezmoi sudo guards and the athena policy tightening

[Bead Pages](../README.md) / [sase-110](README.md) / sase-110.7

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0kl](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0kl.md) · **Assignee:** `sase-110.7` · **Size:** medium
**Created:** 2026-09-14 11:33:19 EDT
**Plan:** [202609/agent\_sudo\_requests.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_sudo_requests.md)

## Description

athena-policy: guard the chezmoi run_onchange scripts against password-required sudo, then live-tighten athena by replacing the NOPASSWD:ALL sudoers rule and setting ptrace_scope=1 through the shipped /sase_sudo flow itself.

## Dependencies

- **Depends on:** [sase-110.4](sase-110.4.md) ◐ · ⧖ 2026-09-14
- **Depends on:** [sase-110.5](sase-110.5.md) ✓ · ⧖ 2026-09-14
- **Blocks:** [sase-110.8](sase-110.8.md) ◐ · ⧖ 2026-09-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-110.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-110.7/README.md) | [sase-110.7](sase-110.7.md) | 0 |
