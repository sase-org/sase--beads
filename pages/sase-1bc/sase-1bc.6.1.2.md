# Bead: sase-1bc.6.1.2 — Active-tab scope stage and tab-keyed panel state

[Bead Pages](../README.md) / [sase-1bc.6.1](sase-1bc.6.1.md) / sase-1bc.6.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1bc.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.6.md) · **Assignee:** `sase-1bc.6.1.2` · **Size:** medium
**Created:** 2026-09-27 13:46:08 EDT · **Closed:** 2026-09-27 16:51:10 EDT
**Plan:** [202609/agent\_tabs\_scope.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_tabs_scope.md)

## Description

scope-stage: cache the tab-independent query result and add the active-tab scope stage in the inline and worker finalize paths; add the scope to PreparedApplySnapshot and the stale token; route every direct _agents mutation through the cached result; key the panel-index memo, AgentPanelFoldScope (fold persistence v3 to v4), session-sticky panels, and selection memory by tab scope.

## Notes

[2026-09-27T19:11:21Z · sase-1bc.6.1.2] PROPOSED FOLLOW-UP: symvision gate fails on clean base tree too (usage_windows.py external sase-telegram refs: usage_windows_report, resolve_usage_provider, request_usage_windows_refresh, live_usage_refresh_operations) — pre-existing, unrelated to scope-stage

[2026-09-27T19:42:35Z · sase-1bc.6.1.2] PROPOSED FOLLOW-UP: tests/ace/tui/test_agent_completion.py has 9 failures identical on the clean base tree (candidate ordering/naming assertions) — pre-existing, unrelated to scope-stage

[2026-09-27T20:22:33Z · sase-1bc.6.1.2] PROPOSED FOLLOW-UP: 3 failures identical on clean base tree (test_agent_header_panel overflowing-header scroll claim; 2 directive-completion absence tests) — pre-existing, unrelated to scope-stage

[2026-09-27T20:28:40Z · sase-1bc.6.1.2] PROPOSED FOLLOW-UP: tests/test_keymaps_e2e.py::test_remapped_navigation_key fails identically on the clean base tree — pre-existing, unrelated to scope-stage

[2026-09-27T20:30:33Z · sase-1bc.6.1.2] PROPOSED FOLLOW-UP: tests/test_timezone_display_guard.py fails identically on the clean base tree (decks instance_card + finalizers cli datetime sites) — pre-existing, unrelated to scope-stage

[2026-09-27T20:51:10Z · sase-1bc.6.1.2] scope-stage done: cached tab-independent query result + active-tab scope in inline/worker finalize (plan carries both lists + index), scope in snapshot/stale token, all _agents mutations via remove_agents_from_views, panel memo/folds/sticky/selection keyed by tab scope, fold persistence v4 with v1-v3 default-tab decode. Verified: new tests/ace/tui/test_agent_tab_scope.py 17 passed; full diff-scoped selection (~9043 tests) green except base-identical pre-existing failures (completion x9, header/directive x3, keymaps x1, timezone x1, symvision usage_windows gate) recorded as PROPOSED FOLLOW-UP notes; ruff+mypy clean on 5105 files; no epic-symbol leftovers. Flag-off goldens: no render code touched, scope is identity (visual lane blocked by environmental Rust rebuild lock). Follow-on symbols for phase 3: _rescope_agents_to_active_tab, _active_agent_tab, AgentTabScope/ALL_AGENT_TABS.

## Dependencies

- **Depends on:** [sase-1bc.6.1.1](sase-1bc.6.1.1.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bc.6.1.3](sase-1bc.6.1.3.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.6.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bc.6.1.2/README.md) | [sase-1bc.6.1.2](sase-1bc.6.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`59f5eff`](https://github.com/sase-org/sase/commit/59f5eff1660acfb36c8eaa040c7e6a4fcd71ee59) | feat(agent-tabs): active-tab scope stage and tab-keyed panel state (sase-1bc.6.1.2) | [sase-1bc.6.1.2](sase-1bc.6.1.2.md) | 2026-09-27 16:53:15 EDT |
