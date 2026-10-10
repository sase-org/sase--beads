# Bead: sase-1jc.5 — Stabilize agent-session and turn compatibility aliases

[Bead Pages](../README.md) / [sase-1jc](README.md) / sase-1jc.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zb.md) · **Assignee:** `sase-1jc.5` · **Size:** medium
**Created:** 2026-10-09 22:28:25 EDT
**Plan:** [202610/retire\_all\_feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202610/retire_all_feature_flags.md)

## Description

identity-aliases: Follow phase 5 and the shared removal checklist. Retire legacy_agent_family_syntax and legacy_sase_shell_syntax; close sase-18l and sase-1ar. Keep all currently enabled alias normalization, including Rust's family keyword alias, and delete the flag-off rejection branches. Preserve canonical output, conflict validation, and old durable records. Do not interpret legacy flag names as permission to remove their enabled compatibility behavior.

## Dependencies

- **Depends on:** [sase-1jc.4](sase-1jc.4.md) ◐ · ⧖ 2026-10-09
- **Blocks:** [sase-1jc.6](sase-1jc.6.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jc.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.5/README.md) | [sase-1jc.5](sase-1jc.5.md) | 0 |
