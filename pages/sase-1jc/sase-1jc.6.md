# Bead: sase-1jc.6 — Remove the legacy live Agents query implementation

[Bead Pages](../README.md) / [sase-1jc](README.md) / sase-1jc.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zb.md) · **Assignee:** `sase-1jc.6` · **Size:** medium
**Created:** 2026-10-09 22:28:25 EDT
**Plan:** [202610/retire\_all\_feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202610/retire_all_feature_flags.md)

## Description

agents-query: Follow phase 6 and the shared removal checklist. Retire agents_unified_query and close sase-zg. Make the Rust agents-live profile and FilterBar unconditional. Delete the legacy live parser/evaluator, QueryEditModal, and dependent dead state after checking every consumer. Preserve current saved-query compatibility, history scoping, Rust pushdown, and asynchronous refresh performance. Verify behavior and affected visual fixtures.

## Dependencies

- **Depends on:** [sase-1jc.5](sase-1jc.5.md) ◐ · ⧖ 2026-10-09
- **Blocks:** [sase-1jc.7](sase-1jc.7.md) ◐ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jc.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.6/README.md) | [sase-1jc.6](sase-1jc.6.md) | 0 |
