# Bead: sase-1kl.1 — Fix the test-lane failures blocking Full CI and Master Gate

[Bead Pages](../README.md) / [sase-1kl](README.md) / sase-1kl.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.106](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.106.md) · **Assignee:** `sase-1kl.1` · **Size:** medium
**Created:** 2026-10-13 14:15:35 EDT
**Plan:** [202610/v0\_18\_0\_release\_unblock.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_release_unblock.md)

## Description

test-flakes: fix the New Project source/create debounce races and the sudo canary length false positive that redden today's Full CI test lanes, re-inventory newer red runs, and root-cause the recent Master Gate tip flakes where the cause is a test wait or fixture.

## Dependencies

- **Blocks:** [sase-1kl.4](sase-1kl.4.md) ◐ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kl.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1kl.1/README.md) | [sase-1kl.1](sase-1kl.1.md) | 0 |
