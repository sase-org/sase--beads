# Bead: sase-bd.5 — Projection drift detection and repair

[Bead Pages](../README.md) / [sase-bd](README.md) / sase-bd.5

**Status:** ◐ in_progress · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bd.5` · **Size:** medium
**Created:** 2026-07-30 17:44:53 UTC
**Plan:** [202607/bead\_close\_integrity.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_close_integrity.md)

## Description

doctor-projection: teach doctor to compare `issues.jsonl` against the reduction of the canonical streams, census redundant close events with a recent-window rate, and add a guarded `--fix-projection` repair that refuses any diff outside the expected shape.

## Dependencies

- **Depends on:** [sase-bd.1](sase-bd.1.md) ✓
- **Blocks:** [sase-bd.7](sase-bd.7.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bd.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bd.5/README.md) | [sase-bd.5](sase-bd.5.md) | 0 |
