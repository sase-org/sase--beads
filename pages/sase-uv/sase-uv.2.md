# Bead: sase-uv.2 — Take provider discovery off the keystroke path

[Bead Pages](../README.md) / [sase-uv](README.md) / sase-uv.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ex](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ex.md) · **Assignee:** `sase-uv.2` · **Size:** medium
**Created:** 2026-08-27 12:26:44 EDT · **Closed:** 2026-08-27 13:59:13 EDT
**Plan:** [202608/ace\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_tui_responsiveness.md)

## Description

keypath: make accent/icon resolution for fixed panes table-driven, memoize fixed descriptors, and convert resolve_artifacts_subtabs to serve-stale-revalidate-in-background so no keystroke can fork git.

## Notes

[2026-08-27T17:58:28Z · sase-uv.2] PROPOSED FOLLOW-UP: just check full-lane is red outside the keypath phase — governed full pytest reached 37,814 passes but reported unrelated agent/core schema and metadata failures, then stuck in test_archive_publication_order_survives_inverted_scheduling xdist shutdown.

[2026-08-27T17:59:13Z · sase-uv.2] Verified 53 focused/adjacent TUI tests pass; ruff/test-wait lint lanes passed under just check before full pytest; epic-symbols clean. just check full pytest did not pass due unrelated agent/core schema and plan-approval gate-poller failures recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-uv.3](sase-uv.3.md) ✓ · ⧖ 2026-08-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-uv.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-uv.2/README.md) | [sase-uv.2](sase-uv.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`795afdc`](https://github.com/sase-org/sase/commit/795afdc5faee02e63f5753f3ca7e822797b29538) | fix(ace): keep artifact discovery off key path | [sase-uv.2](sase-uv.2.md) | 2026-08-27 14:03:06 EDT |
