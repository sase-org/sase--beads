# Bead: sase-16z.9.3 — Floor-aware freshness for the TUI header usage indicator

[Bead Pages](../README.md) / [sase-16z.9](sase-16z.9.md) / sase-16z.9.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-16z.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16z.land.md) · **Assignee:** `sase-16z.9.3` · **Size:** small
**Created:** 2026-09-23 16:32:22 EDT
**Plan:** [202609/usage\_collection\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_collection_landing_fixes.md)

## Description

header-floor-freshness: move the sase-core pin past core-indicator-floors, pass per-provider polling floors captured off the UI thread into the header indicator projection, and test and document that the header uses `max(refresh_seconds, floor)` freshness like the CLI and Models panel.

## Dependencies

- **Depends on:** [sase-16z.9.1](sase-16z.9.1.md) ◐ · ⧖ 2026-09-23
- **Depends on:** [sase-16z.9.2](sase-16z.9.2.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.9.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.9.3/README.md) | [sase-16z.9.3](sase-16z.9.3.md) | 0 |
