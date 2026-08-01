# Bead: sase-da.1 — Fair, configurable store-lock waits in sase-core

[Bead Pages](../README.md) / [sase-da](README.md) / sase-da.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.r5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.r5/README.md) · **Assignee:** `sase-da.1` · **Size:** medium
**Created:** 2026-08-01 13:03:54 UTC
**Plan:** [202608/bead\_store\_lock\_contention.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_store_lock_contention.md)

## Description

store_lock: replace the 2s hardcoded try-lock poll in the Rust bead-mutation, task-store, and prompt-stash locks with a capped-backoff wait whose bound is a long, env-overridable default, and record holder identity so an expired wait names its blocker.

## Dependencies

- **Blocks:** [sase-da.4](sase-da.4.md) ◐
- **Blocks:** [sase-da.5](sase-da.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-da.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-da.1/README.md) | [sase-da.1](sase-da.1.md) | 0 |
