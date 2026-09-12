# Bead: sase-zu.4 — TUI full-history loads read the index instead of walking the filesystem

[Bead Pages](../README.md) / [sase-zu](README.md) / sase-zu.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.05.f0` · **Assignee:** `sase-zu.4` · **Size:** small
**Created:** 2026-09-12 10:35:46 EDT · **Closed:** 2026-09-12 17:33:58 EDT
**Plan:** [202609/agent\_query\_load\_tiering.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_query_load_tiering.md)

## Description

tui_full_history: route the TUI's full-history load through the artifact index with a candidate filter, keeping the bounded source scan as an explicit fallback.

## Notes

[2026-09-12T21:33:58Z · sase-zu.4] Implemented agents_index_full_history so TUI full-history loads use a revalidated artifact-index query with candidate filters and source-scan fallbacks; verified with .venv/bin/python -m pytest -q tests/test_agent_loader_query_window.py tests/test_agent_load_tiering_harness.py tests/test_github_cli.py, just check, and sase bead epic-symbols sase-zu.4.

[2026-09-12T21:34:58Z · sase-zu.4] PROPOSED FOLLOW-UP: Core wheel setup can regress to an older published sase-core-rs after local build — just install built 0.34.24, but the environment initially still had 0.34.22 until the cached local wheel was explicitly reinstalled; just check also reports a stale core-floor warning for declared_floor 0.34.21.

## Dependencies

- **Depends on:** [sase-zu.3](sase-zu.3.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zu.6](sase-zu.6.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zu.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zu.4/README.md) | [sase-zu.4](sase-zu.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f609668`](https://github.com/sase-org/sase/commit/f609668b7276bccd14ccf2a5d78051c1f7dea6de) | feat(agents): load full history from artifact index | [sase-zu.4](sase-zu.4.md) | 2026-09-12 17:36:42 EDT |
