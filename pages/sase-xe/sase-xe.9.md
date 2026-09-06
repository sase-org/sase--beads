# Bead: sase-xe.9 — Durable follow subscriptions with family continuity

[Bead Pages](../README.md) / [sase-xe](README.md) / sase-xe.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gq.md) · **Assignee:** `sase-xe.9` · **Size:** medium
**Created:** 2026-09-06 14:06:45 EDT
**Plan:** [202609/remote\_dispatch\_fleet.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_fleet.md)

## Description

follow-store: persist viewer-local follow records keyed by origin and logical agent/family identity, promote singleton follows to the family identity when a family forms, make explicit unfollow tombstones win over automatic re-creation, and implement the shared Focus/Fleet running-count calculations over authoritative summaries with unknown-host propagation.

## Dependencies

- **Blocks:** [sase-xe.11](sase-xe.11.md) ◐ · ⧖ 2026-09-06
- **Depends on:** [sase-xe.2](sase-xe.2.md) ✓ · ⧖ 2026-09-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.9/README.md) | [sase-xe.9](sase-xe.9.md) | 0 |
