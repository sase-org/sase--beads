# Bead: sase-ak.2 — Shared tribe wait binding resolver

[Bead Pages](../README.md) / [sase-ak](README.md) / sase-ak.2

**Status:** ◐ in_progress · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ak.2` · **Size:** medium
**Created:** 2026-07-28 21:05:20 UTC
**Plan:** [202607/tribe\_wait\_reference\_validation\_and\_display.md](https://github.com/sase-org/sase--plans/blob/main/202607/tribe_wait_reference_validation_and_display.md)

## Description

tribe-wait-binding: extract the `tribe_candidate` ordering and aggregation rules into a pure, snapshot-driven resolver in Python core that both the wait index and the TUI can call, and add a pending/bound/reserved classification the display layer can consume without touching disk.

## Dependencies

- **Blocks:** [sase-ak.3](sase-ak.3.md) ◎

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ak.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ak.2/README.md) | [sase-ak.2](sase-ak.2.md) | 0 |
