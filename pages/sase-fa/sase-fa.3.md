# Bead: sase-fa.3 — Narrow the durable outbox back to agent-hood retries

[Bead Pages](../README.md) / [sase-fa](README.md) / sase-fa.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.t4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.t4/README.md) · **Assignee:** `sase-fa.3` · **Size:** medium
**Created:** 2026-08-05 14:26:37 EDT
**Plan:** [202608/revert\_async\_sidecar\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_async_sidecar_publication.md)

## Description

queue: drop the `bead_pages`, `plan_header`, and `sidecar_push` request kinds, bump the outbox schema so existing v4 files load without resurrecting them, and revert doctor, ACE, status, and prompt-archive validation to agent-hood-only semantics.

## Dependencies

- **Depends on:** [sase-fa.2](sase-fa.2.md) ✓
- **Blocks:** [sase-fa.5](sase-fa.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fa.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fa.3/README.md) | [sase-fa.3](sase-fa.3.md) | 0 |
