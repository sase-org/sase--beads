# Bead: sase-mg.2 — Replace current-agent list with show and build historical list

[Bead Pages](../README.md) / [sase-mg](README.md) / sase-mg.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02u.md) · **Assignee:** `sase-mg.2` · **Size:** medium
**Created:** 2026-08-15 15:36:56 EDT · **Closed:** 2026-08-15 17:01:23 EDT
**Plan:** [202608/powerful\_variables.md](https://github.com/sase-org/sase--plans/blob/main/202608/powerful_variables.md)

## Description

show-and-list-cli: add the show command, redesign list around the core history query, and provide rich and machine-readable output with filtering and limits.

## Notes

[2026-08-15T21:00:52Z · sase-mg.2] PROPOSED FOLLOW-UP: ratchet sase-core-rs floor to >=0.27.8 once the linked sase-core checkout is versioned to match — published 0.27.8 already ships query_agent_output_variable_history, but this workspace core is still 0.27.7 so the floor cannot move without failing just check

[2026-08-15T21:01:23Z · sase-mg.2] Implemented sase var show (direct current-artifact read plus newest exact-name resolution) and historical sase var list on the core history query; verified parser aliases/invalid limits/JSON/dates, identity fallbacks, direct-read freshness, project display names, filter combinations, pretty/json/jsonl, color never/always, Unicode/multiline/container values, and zero/unlimited limits; just check passed (lint + 1023-file scoped suite).

[2026-08-15T21:02:13Z · sase-mg.2] Verified sase var show [AGENT_NAME] (current-agent SASE_ARTIFACTS_DIR freshness, named-agent newest exact match, --project, unknown-agent error, empty-state) and sase var list (unique keys newest-first, filters --agent/--key/--project/--since/--until/--value/--value-json/--hidden/--reverse/--limit, pretty/json/jsonl, color gating, truncation). Parser/handler/history-wire tests plus just check (lint + scoped suite). Bare sase var still delegates to list. Artifact index schema pin 21. Core floor left at current checkout until sase-core-rs can ratchet to >=0.27.8.

## Dependencies

- **Depends on:** [sase-mg.1](sase-mg.1.md) ✓ · ⧖ 2026-08-15
- **Blocks:** [sase-mg.3](sase-mg.3.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mg.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mg.2/README.md) | [sase-mg.2](sase-mg.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`57af5d3`](https://github.com/sase-org/sase/commit/57af5d3ed0c0ca5557ec3d2421714172d7ded28a) | feat(var): add historical list and current-agent show | [sase-mg.2](sase-mg.2.md) | 2026-08-15 17:03:00 EDT |
