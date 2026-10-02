# Bead: sase-1es.2 — Quadratic scans, span memoization, and the dismissed-view leak

[Bead Pages](../README.md) / [sase-1es](README.md) / sase-1es.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v9.md) · **Assignee:** `sase-1es.2` · **Size:** medium
**Created:** 2026-10-02 08:37:46 EDT
**Plan:** [202610/pager\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/pager_performance.md)

## Description

scan-leak-fixes: fix the theme-watcher leak that keeps every closed pager alive, make link scanning and window-label row lookups near-linear, memoize per-section target spans and live-pin digests, and stop trail entries from retaining search copies.

## Dependencies

- **Depends on:** [sase-1es.1](sase-1es.1.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1es.5](sase-1es.5.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1es.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1es.2/README.md) | [sase-1es.2](sase-1es.2.md) | 0 |
