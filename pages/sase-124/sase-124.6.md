# Bead: sase-124.6 — Bounded marker polling so in-flight node status converges without broad loads

[Bead Pages](../README.md) / [sase-124](README.md) / sase-124.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0mc](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0mc.md) · **Assignee:** `sase-124.6` · **Size:** medium
**Created:** 2026-09-17 10:59:46 EDT
**Plan:** [202609/agents\_tab\_freshness.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_freshness.md)

## Description

inflight-status: extend the STARTING-row 1 s stat poll to all in-flight rows so marker transitions schedule exact artifact-delta refreshes within seconds even when inotify misses events.

## Dependencies

- **Depends on:** [sase-124.1](sase-124.1.md) ✓ · ⧖ 2026-09-17
- **Blocks:** [sase-124.7](sase-124.7.md) ◐ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-124.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-124.6/README.md) | [sase-124.6](sase-124.6.md) | 0 |
