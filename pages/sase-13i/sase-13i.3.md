# Bead: sase-13i.3 — Stop incomplete bounded loads from replacing a larger cache

[Bead Pages](../README.md) / [sase-13i](README.md) / sase-13i.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ns](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ns.md) · **Assignee:** `sase-13i.3` · **Size:** medium
**Created:** 2026-09-19 10:43:15 EDT · **Closed:** 2026-09-20 06:48:44 EDT
**Plan:** [202609/epic\_tribe\_panel\_flicker.md](https://github.com/sase-org/sase--plans/blob/main/202609/epic_tribe_panel_flicker.md)

## Description

removal-authority: patch same-query bounded loads regardless of has_more, keep a nonempty cache across a bounded zero, clear the complete-history latch only on a committed-query change, and converge revalidate with auto-refresh.

## Notes

[2026-09-20T10:47:47Z · sase-13i.3] PROPOSED FOLLOW-UP: repro schema lacks committed-query key — incomplete_nonempty_to_empty invariant cannot exempt a legitimate query change; add history_query_key to ReproLoadState.

[2026-09-20T10:48:17Z · sase-13i.3] PROPOSED FOLLOW-UP: repro schema lacks committed-query key — incomplete_nonempty_to_empty invariant cannot exempt a legitimate query change; add history_query_key to ReproLoadState.

[2026-09-20T10:48:44Z · sase-13i.3] Same-query bounded loads now patch regardless of has_more (bounded zero keeps cache, traces empty_incomplete_apply_ignored, one revalidate); latch cleared only on committed-query change via new _agents_applied_query_key; added incomplete_nonempty_to_empty invariant; new/updated tests in test_agents_tab_apply_boundary.py pass (tests/ace/tui, tests/perf: 3785 pass; 2 unrelated long-tmp-path wrap failures). just check blocked by pre-existing mypy (tmux) and symvision failures in untouched files.

## Dependencies

- **Depends on:** [sase-13i.1](sase-13i.1.md) ✓ · ⧖ 2026-09-19
- **Blocks:** [sase-13i.4](sase-13i.4.md) ◐ · ⧖ 2026-09-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-13i.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-13i.3/README.md) | [sase-13i.3](sase-13i.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9231c93`](https://github.com/sase-org/sase/commit/9231c9352aef2002b152da037905c3d0f662d46c) | fix(tui): stop incomplete bounded loads from replacing a larger cache | [sase-13i.3](sase-13i.3.md) | 2026-09-20 06:49:50 EDT |
