# Bead: sase-127.2 — Incremental panel refresh with an active filter query

[Bead Pages](../README.md) / [sase-127](README.md) / sase-127.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ml](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ml.md) · **Assignee:** `sase-127.2` · **Size:** medium
**Created:** 2026-09-17 16:26:26 EDT · **Closed:** 2026-09-17 17:18:03 EDT
**Plan:** [202609/agents\_tab\_flicker.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_flicker.md)

## Description

incremental-under-search: allow the incremental display diff path when the search query text is unchanged, keep a distinct full-rebuild fallback for query changes, and cover both with tests.

## Notes

[2026-09-17T21:18:03Z · sase-127.2] Verified unchanged active search uses incremental refresh without update_list/full rebuild, changed search query records search_query_changed and rebuilds once; ran focused pytest and just check (scoped escalated to full suite) successfully; epic-symbols has no entries.

## Dependencies

- **Blocks:** [sase-127.4](sase-127.4.md) ✓ · ⧖ 2026-09-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-127.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-127.2/README.md) | [sase-127.2](sase-127.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`155aeee`](https://github.com/sase-org/sase/commit/155aeee2efe67b653c4c715888716a116401fdaa) | fix(tui): allow incremental agent refresh under stable search | [sase-127.2](sase-127.2.md) | 2026-09-17 17:20:00 EDT |
