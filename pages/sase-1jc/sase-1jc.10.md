# Bead: sase-1jc.10 — Stabilize provider instruction and execution channels

[Bead Pages](../README.md) / [sase-1jc](README.md) / sase-1jc.10

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zb.md) · **Assignee:** `sase-1jc.10` · **Size:** medium
**Created:** 2026-10-09 22:28:26 EDT
**Plan:** [202610/retire\_all\_feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202610/retire_all_feature_flags.md)

## Description

provider-instructions: Follow phase 10 and the shared removal checklist. Retire muse_synchronous_shell, grok_rules_delivery, claude_helper_channel, and instruction_shadow_render; close sase-178, sase-1gv, sase-1gw, and sase-1h4. Keep synchronous Muse execution, root Grok rules, supported Claude helper channels/guards, and fail-open shadow rendering. Delete flag resolution and disabled variants without converting shadow rendering into a new delivery cutover.

## Dependencies

- **Blocks:** [sase-1jc.11](sase-1jc.11.md) ◐ · ⧖ 2026-10-09
- **Depends on:** [sase-1jc.9](sase-1jc.9.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jc.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.10/README.md) | [sase-1jc.10](sase-1jc.10.md) | 0 |
