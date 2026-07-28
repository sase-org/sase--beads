# Bead: sase-am.3 — Consolidate lanes without losing coverage

[Bead Pages](../README.md) / [sase-am](README.md) / sase-am.3

**Status:** ◎ claimed · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-am.3` · **Size:** medium
**Created:** 2026-07-28 22:05:58 UTC
**Plan:** [202607/ci\_flakiness\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202607/ci_flakiness_redesign.md)

## Description

lane-consolidation: merge the three perf-floor jobs into one, delete the redundant install-smoke/bead-backend/build/fmt-md-check jobs after folding their unique steps into neighbors, run the visual suite exactly once per run, build docs once per event, and serialize docs deploys.

## Dependencies

- **Depends on:** [sase-am.2](sase-am.2.md) ◐
- **Blocks:** [sase-am.4](sase-am.4.md) ◎

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-am.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-am.3/README.md) | [sase-am.3](sase-am.3.md) | 0 |
