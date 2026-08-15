# Bead: sase-m9.3.1.2 — Migrate patch and agent proc producers

[Bead Pages](../README.md) / [sase-m9.3.1](sase-m9.3.1.md) / sase-m9.3.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m9.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m9.3.md) · **Assignee:** `sase-m9.3.1.2` · **Size:** large
**Created:** 2026-08-15 15:17:09 EDT
**Plan:** [202608/ace\_proc\_ownership.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_proc_ownership.md)

## Description

migrate-patch-and-agent-producers: move ACE patch/status/rebase/sync/rewind/mail and agent launch, approve, revert, cleanup, wait, rename, and tribe-assignment operations onto the durable domain commands; preserve optimistic UI behavior, reconstruct completion from result envelopes, and translate patch identity, dedup, exclusive scopes, workspace claims, AXE slots, and agent metadata locks into atomically reserved namespaced concurrency keys.

## Dependencies

- **Depends on:** [sase-m9.3.1.1](sase-m9.3.1.1.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-m9.3.1.4](sase-m9.3.1.4.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m9.3.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m9.3.1.2/README.md) | [sase-m9.3.1.2](sase-m9.3.1.2.md) | 0 |
