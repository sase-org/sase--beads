# Bead: sase-o8.4 — Warm cache, menu, and settings wiring

[Bead Pages](../README.md) / [sase-o8](README.md) / sase-o8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.04e](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.04e.md) · **Assignee:** `sase-o8.4` · **Size:** medium
**Created:** 2026-08-17 06:01:53 EDT · **Closed:** 2026-08-17 08:24:51 EDT
**Plan:** [202608/placeholder\_completion\_ranking.md](https://github.com/sase-org/sase--plans/blob/main/202608/placeholder_completion_ranking.md)

## Description

wiring: hold the placeholder index in the app-global warm cache, feed ranked saved tags through the Rust completion engine and reattach their ranking evidence, keep Ctrl+D deletion instant, and add the two ranking settings.

## Notes

[2026-08-17T12:24:24Z · sase-o8.4] PROPOSED FOLLOW-UP: retarget or consume monitor_row_agent_name — just check failed on a stale sase-o9.2 epic-symbol after that phase closed; the symbol is still unused and is now whitelisted as sase-o9.4(monitor_row_agent_name) because sase-o9.4 (Enter opens the monitor agent) is the in-progress consumer. That phase should use the helper and delete the Justfile entry.

[2026-08-17T12:24:51Z · sase-o8.4] Warm cache now holds CommonPlaceholderIndex (list derived alongside it); saved tags are ranked through the Rust engine and reattached as PlaceholderRankingMetadata in smart mode; recent mode keeps stored order with no metadata; Ctrl+D drops the warm index instantly without waiting for a store rebuild; placeholder_ranking/placeholder_ranking_signals parse, schema, and default_config default to smart/true. just check passed after Justfile/schema edits escalated to the full suite.

[2026-08-17T12:25:54Z · sase-o8.4] Warm cache holds CommonPlaceholderIndex; saved tags rank through the Rust engine with PlaceholderRankingMetadata in smart mode; recent mode keeps stored order; Ctrl+D drops the warm index instantly; placeholder_ranking/placeholder_ranking_signals parse, schema, and default_config default to smart/true. just check passed after Justfile/schema edits escalated to the full suite.

## Dependencies

- **Depends on:** [sase-o8.3](sase-o8.3.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-o8.5](sase-o8.5.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-o8.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-o8.4/README.md) | [sase-o8.4](sase-o8.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`68aaa68`](https://github.com/sase-org/sase/commit/68aaa68634d2462af15fea43c10c9e8dc62a549c) | feat(ace-tui): rank saved placeholder tags from the warm cache | [sase-o8.4](sase-o8.4.md) | 2026-08-17 08:27:25 EDT |
