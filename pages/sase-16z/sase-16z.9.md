# Bead: sase-16z.9 — Finish usage-window collection landing fixes and floor-aware header freshness

[Bead Pages](../README.md) / [sase-16z](README.md) / sase-16z.9

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-16z.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16z.land.md) · **Assignee:** `sase-16z.9.land`
**Created:** 2026-09-23 16:32:18 EDT
**Plan:** [202609/usage\_collection\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_collection_landing_fixes.md)

## Description

The usage-window collection work from epic sase-16z is actually complete. Its epic-introduced symvision failures are gone. agy and grok capability-cache entries hit in production. Rate-limit evidence on transport failures is classified. The stale chop test no longer spawns real provider CLIs. The TUI header usage indicator uses the same floor-aware freshness (`max(refresh_seconds, floor)`) as the CLI and Models panel, so a provider polled at its floor never shows as stale or unknown between probes.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.9.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.9.land/README.md) | [sase-16z.9](sase-16z.9.md) | 0 |
