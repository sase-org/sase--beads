# Bead: sase-k2.6 — Bounded per-pass cost for the PR mirror

[Bead Pages](../README.md) / [sase-k2](README.md) / sase-k2.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yn](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yn/README.md) · **Assignee:** `sase-k2.6` · **Size:** medium
**Created:** 2026-08-12 11:31:05 EDT
**Plan:** [202608/external\_mirror\_refinement.md](https://github.com/sase-org/sase--plans/blob/main/202608/external_mirror_refinement.md)

## Description

perf: stop re-reading and re-parsing the whole active-plus-archive ProjectSpec index once per mutation in both the sync loop and the importer, replacing it with one locked batch apply over an incrementally maintained index.

## Dependencies

- **Depends on:** [sase-k2.1](sase-k2.1.md) ✓ · ⧖ 2026-08-12
- **Depends on:** [sase-k2.5](sase-k2.5.md) ✓ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k2.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k2.6/README.md) | [sase-k2.6](sase-k2.6.md) | 0 |
