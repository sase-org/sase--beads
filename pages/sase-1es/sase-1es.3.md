# Bead: sase-1es.3 — Cold-path import and startup diet

[Bead Pages](../README.md) / [sase-1es](README.md) / sase-1es.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v9.md) · **Assignee:** `sase-1es.3` · **Size:** medium
**Created:** 2026-10-02 08:37:48 EDT
**Plan:** [202610/pager\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/pager_performance.md)

## Description

cold-path-diet: make `sase.pager` imports lazy, move pure helpers out of `sase.ace.tui` into leaf modules, defer heavy imports to use sites, skip interactive-only work in plain mode, and add import-weight regression tests.

## Dependencies

- **Depends on:** [sase-1es.1](sase-1es.1.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1es.5](sase-1es.5.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1es.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1es.3/README.md) | [sase-1es.3](sase-1es.3.md) | 0 |
