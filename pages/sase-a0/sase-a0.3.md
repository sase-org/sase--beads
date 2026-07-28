# Bead: sase-a0.3 — Give the mark\_all\_read anchor a documented variance factor

[Bead Pages](../README.md) / [sase-a0](README.md) / sase-a0.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a0.3` · **Size:** small
**Created:** 2026-07-27 16:02:11 UTC · **Closed:** 2026-07-27 16:11:10 UTC
**Plan:** [202607/fix\_ci\_failures.md](https://github.com/sase-org/sase--plans/blob/main/202607/fix_ci_failures.md)

## Description

perffloor: add a per-anchor `rust_slowdown_factor` override with a written rationale for the one write-heavy notification anchor whose ceiling has no slack, matching the mechanism already used for its two sibling anchors.

## Dependencies

- **Blocks:** [sase-a0.4](sase-a0.4.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a0.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a0.3/README.md) | [sase-a0.3](sase-a0.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`55a2b03`](https://github.com/sase-org/sase/commit/55a2b032160da180f25e929e60170f7a811bac95) | test(perf): add mark\_all\_read floor variance override (sase-a0.3) | [sase-a0.3](sase-a0.3.md) | 2026-07-27 16:13:02 |
