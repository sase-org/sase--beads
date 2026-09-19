# Bead: sase-13i.2 — Key AgentList widgets by tribe and stop blanking untouched panels

[Bead Pages](../README.md) / [sase-13i](README.md) / sase-13i.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ns](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ns.md) · **Assignee:** `sase-13i.2` · **Size:** medium
**Created:** 2026-09-19 10:43:13 EDT · **Closed:** 2026-09-19 12:53:07 EDT
**Plan:** [202609/epic\_tribe\_panel\_flicker.md](https://github.com/sase-org/sase--plans/blob/main/202609/epic_tribe_panel_flicker.md)

## Description

tribe-stable-widgets: give each tribe a stable widget id, insert or remove one panel without rebuilding siblings, skip clear_options on unchanged row sets, and finish the standing-query row-remove path.

## Notes

[2026-09-19T16:53:07Z · sase-13i.2] Tribe-stable AgentList ids (agent-list-panel-{public_tribe_name}); sibling insert/remove without update_list/clear_options on untouched panels; session-sticky empty strips under the same query; standing-query row-remove no longer bails on active_search. Verified: targeted widget/diff/kill tests plus just check lint/mypy; scoped suite 43464 passed (1 unrelated ace_handler executor-join timing flake, 5/5 isolated retries green).

## Dependencies

- **Blocks:** [sase-13i.4](sase-13i.4.md) ◐ · ⧖ 2026-09-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-13i.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-13i.2/README.md) | [sase-13i.2](sase-13i.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`45a7895`](https://github.com/sase-org/sase/commit/45a7895b6b98360ac447352a570c75ca1ea7a180) | feat(tui): key AgentList widgets by tribe and skip sibling rebuilds | [sase-13i.2](sase-13i.2.md) | 2026-09-19 12:54:53 EDT |
