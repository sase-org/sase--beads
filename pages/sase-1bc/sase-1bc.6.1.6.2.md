# Bead: sase-1bc.6.1.6.2 — Back-anchors, failed-reveal restore, and fold-aware reveal for every cross-tab jump

[Bead Pages](../README.md) / [sase-1bc.6.1.6](sase-1bc.6.1.6.md) / sase-1bc.6.1.6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1bc.6.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.6.1.land.md) · **Assignee:** `sase-1bc.6.1.6.2` · **Size:** medium
**Created:** 2026-09-27 20:11:31 EDT · **Closed:** 2026-09-28 01:28:31 EDT
**Plan:** [202609/agent\_tabs\_scope\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_tabs_scope_repairs.md)

## Description

cross-tab-jump-repairs: save the back-anchor before switching tabs in _try_reveal_agent_row; drop the notification pre-switch in favor of the Node Finder ladder; route the run-log, revive, Files, and link-trail jumps through the fold-expanding reveal with tab restore; restore the tab when a back-jump or a last-launch reveal fails; make the ,j off-tab path reveal-aware; show the off-tab chip on every off-tab Node Finder row; keep flag-off lookups unchanged; add tests for every entry point.

## Notes

[2026-09-28T04:45:43Z · sase-1bc.6.1.6.2--1] PROPOSED FOLLOW-UP: tests/test_agent_revive.py has a pre-existing pyright reportAttributeAccessIssue (lines ~313-317, ~402-406 after this phase's edits): `assert delta is not False` does not narrow `AgentReviveDelta | bool` for pyright, so `.revived_identities`/`.failed`/`.has_changes` accesses on `delta` are flagged as accessing attributes on `Literal[True]`. Pre-existing on HEAD (1ea13da1b3), unrelated to this phase; fix by narrowing with `isinstance(delta, AgentReviveDelta)` or asserting `isinstance` instead of `is not False`.

[2026-09-28T05:27:06Z · sase-1bc.6.1.6.2--1] PROPOSED FOLLOW-UP: tests/test_axe_run_agent_exec_repeat_env.py (6 tests: TestRepeatIterationEnv, TestWaitChatsInjection, TestInheritedVcsInjection) and tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift + test_current_structural_view_matches_checked_in_snapshot fail on the clean base tree (verified via git stash), fully unrelated to agent-tabs/cross-tab-jump-repairs (no overlap with any file this phase touched). No existing task bead found tracking these; needs triage as CI failures.

[2026-09-28T05:28:31Z · sase-1bc.6.1.6.2--1] Verified sase tool run check: fixed a real regression the monitored check caught — _revive_state.py's _select_revived_agent now routes through _try_reveal_agent_row (per plan), but tests/_agent_revive_helpers.py's FakeReviveApp lacked the reveal machinery (MemberJumpNavigationMixin) and never resynced _panel_group after a reload, so 4 revive tests (test_agent_revive.py x3, test_agent_group_revival_execution.py x1) failed. Fixed by mixing MemberJumpNavigationMixin into FakeReviveApp and resyncing _panel_group in _load_agents (mirrors the real _finalize_agent_list -> _refresh_agents_display -> _sync_panel_group guarantee), then updated 4 refresh_calls assertions from [False] to [True, False] to reflect the intentional extra internal refresh _try_reveal_agent_row now fires on a cross-panel/stale-banner reveal (caller's own refresh is still required for the common same-panel case, so it cannot be dropped). Verified: tests/test_agent_revive.py, tests/test_agent_group_revival_execution.py, tests/test_agent_group_revival_e2e.py, tests/ace/tui/test_agent_tab_cross_nav.py all green (51 passed). Re-ran sase tool run check (tool aa5a58b8d2bbb8e7a3813df5d29e8339): all remaining failures are either on the plan's known pre-existing list (test_agent_completion.py + 2 directive-completion tests, test_no_system_clock_display_sites, test_expanded_overflowing_header_claims_half_page_scroll, symvision rail_urgency/rail_tooltip_text) or independently confirmed via git stash to reproduce identically on the clean base tree (test_axe_run_agent_exec_repeat_env.py, completion/test_snapshot.py) — unrelated to any file this phase touched; recorded as PROPOSED FOLLOW-UP notes, along with a pre-existing pyright narrowing nit in test_agent_revive.py. epic-symbols: none for this bead.

## Dependencies

- **Depends on:** [sase-1bc.6.1.6.1](sase-1bc.6.1.6.1.md) ✓ · ⧖ 2026-09-27
- **Blocks:** [sase-1bc.6.1.6.3](sase-1bc.6.1.6.3.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.6.1.6.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.6.1.6.2.md) | [sase-1bc.6.1.6.2](sase-1bc.6.1.6.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3ba7f3b`](https://github.com/sase-org/sase/commit/3ba7f3b22f279a6b900fd76405192841a06f73d7) | fix(ace-tui): repair cross-tab jump reveal/restore paths for agent tabs | [sase-1bc.6.1.6.2](sase-1bc.6.1.6.2.md) | 2026-09-28 01:30:43 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bc.6.1.6.2--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.6.1.6.2.md

<!-- sase:referenced-by:end -->
