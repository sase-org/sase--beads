# Bead: sase-16t.6 — Stitch, Plan/provider, and Patch context queries

[Bead Pages](../README.md) / [sase-16t](README.md) / sase-16t.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pq.md) · **Assignee:** `sase-16t.6` · **Size:** medium
**Created:** 2026-09-23 08:23:36 EDT · **Closed:** 2026-09-23 13:26:38 EDT
**Plan:** [202609/artifact\_link\_jumps.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_jumps.md)

## Description

bounded-panes: acquire-then-reveal for panes whose inventory is bounded. Stitch jumps rewrite to a repo-and-day window, Plan and provider panes use a `path:` context, and Patch jumps show the patch's stack, with Stitches' reveal row read from the unfiltered collection.

## Notes

[2026-09-23T17:26:03Z · sase-16t.6] PROPOSED FOLLOW-UP: symvision flags ExpandedLaunchSegments (src/sase/agent/launch_cwd_segments.py) at HEAD — pre-existing, unrelated to this phase; just check stays red until its owner privatizes it or adds an epic-symbol

[2026-09-23T17:26:38Z · sase-16t.6] bounded-panes acquire-then-reveal done: repo-and-day Stitch window from unfiltered row + acquired facts, path: plan/provider context with deep-archive wait, ancestor:/name: Patch contexts with fold expansion; 12 real-pane AcePage tests pass (8 bounded-panes + grouping updates); fmt+ruff+mypy clean, symvision clean for this phase's symbols, epic-symbols empty

## Dependencies

- **Depends on:** [sase-16t.4](sase-16t.4.md) ✓ · ⧖ 2026-09-23
- **Blocks:** [sase-16t.8](sase-16t.8.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16t.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16t.6/README.md) | [sase-16t.6](sase-16t.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a74e98c`](https://github.com/sase-org/sase/commit/a74e98cfb769e215d32ee5ed915d2683e5b59228) | feat(ace): bounded-panes acquire-then-reveal for Stitch, Plan/provider, and Patch jumps | [sase-16t.6](sase-16t.6.md) | 2026-09-23 13:28:34 EDT |
