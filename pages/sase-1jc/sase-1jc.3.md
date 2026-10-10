# Bead: sase-1jc.3 — Make queue capacity budgets unconditional

[Bead Pages](../README.md) / [sase-1jc](README.md) / sase-1jc.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zb.md) · **Assignee:** `sase-1jc.3` · **Size:** medium
**Created:** 2026-10-09 22:28:24 EDT
**Plan:** [202610/retire\_all\_feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202610/retire_all_feature_flags.md)

## Description

queue-budget: Follow phase 3 and the shared removal checklist. Retire queue_capacity_budget and close sase-zv across Rust parsing/admission/editor behavior and Python launch, bead, and TUI adapters. Delete the Off threshold semantics and finished launch/editor flag plumbing, including already-retired constant shims where proven unused. Preserve supported persisted queue records and percent-hold behavior. Verify the Rust core and Python checkout sequentially.

## Dependencies

- **Depends on:** [sase-1jc.2](sase-1jc.2.md) ◐ · ⧖ 2026-10-09
- **Blocks:** [sase-1jc.4](sase-1jc.4.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jc.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.3/README.md) | [sase-1jc.3](sase-1jc.3.md) | 0 |
