# Bead: sase-1jc.4 — Stabilize macro aliases and strict input types

[Bead Pages](../README.md) / [sase-1jc](README.md) / sase-1jc.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zb.md) · **Assignee:** `sase-1jc.4` · **Size:** medium
**Created:** 2026-10-09 22:28:24 EDT
**Plan:** [202610/retire\_all\_feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202610/retire_all_feature_flags.md)

## Description

macro-contracts: Follow phase 4 and the shared removal checklist. Retire legacy_xprompt_syntax and strict_macro_input_types; close sase-1fj and sase-1g9. Preserve the On branch accepting xprompt aliases, legacy discovery and plugin names, while removing rollout rejection policy and unknown-type-to-line fallback. Make Rust config and LSP normalization follow the same unconditional semantics. Keep duplicate-name and malformed-input errors and durable readers.

## Dependencies

- **Depends on:** [sase-1jc.3](sase-1jc.3.md) ✓ · ⧖ 2026-10-09
- **Blocks:** [sase-1jc.5](sase-1jc.5.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jc.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.4/README.md) | [sase-1jc.4](sase-1jc.4.md) | 0 |
