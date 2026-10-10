# Bead: sase-1jc.9 — Remove legacy monitor-start rollout paths

[Bead Pages](../README.md) / [sase-1jc](README.md) / sase-1jc.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zb](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zb.md) · **Assignee:** `sase-1jc.9` · **Size:** medium
**Created:** 2026-10-09 22:28:26 EDT
**Plan:** [202610/retire\_all\_feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202610/retire_all_feature_flags.md)

## Description

monitor-records: Follow phase 9 and the shared removal checklist. Retire monitor_continuation_records and close sase-102. Every new monitor uses versioned records and capture. Remove the selectable legacy writer/start path, while keeping existing monitor settlement and recovery governed by persisted protocol and sentinel fields. Exercise success/failure delivery, idempotency, recovery, and older persisted monitor records.

## Dependencies

- **Blocks:** [sase-1jc.10](sase-1jc.10.md) ◐ · ⧖ 2026-10-09
- **Depends on:** [sase-1jc.8](sase-1jc.8.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jc.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jc.9/README.md) | [sase-1jc.9](sase-1jc.9.md) | 0 |
