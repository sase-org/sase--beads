# Bead: sase-1tz.2.1.2 — Render one digest line per cause with true totals, coverage, and pruning

[Bead Pages](../README.md) / [sase-1tz.2.1](sase-1tz.2.1.md) / sase-1tz.2.1.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tz.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tz.2.md) · **Assignee:** `sase-1tz.2.1.2` · **Size:** medium
**Created:** 2026-11-19 11:13:26 EST
**Plan:** [202611/noise\_publication\_digests\_tui\_stalls.md](https://github.com/sase-org/sase--plans/blob/main/202611/noise_publication_digests_tui_stalls.md)

## Description

digest_render: the hourly digest snapshots and resets the interval counter atomically. It renders one line per cause with count, first/last time, and a sample under a true-total and coverage header, with no loss after downtime or a crash. Digest files are pruned on a 30-day horizon.

## Dependencies

- **Depends on:** [sase-1tz.2.1.1](sase-1tz.2.1.1.md) ✓ · ⧖ 2026-11-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tz.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tz.2.1.2/README.md) | [sase-1tz.2.1.2](sase-1tz.2.1.2.md) | 0 |
