# Bead: sase-1kx.2 — Make the Full CI visual lane pass and stay clean

[Bead Pages](../README.md) / [sase-1kx](README.md) / sase-1kx.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.10b](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.10b.md) · **Assignee:** `sase-1kx.2` · **Size:** medium
**Created:** 2026-10-14 07:18:03 EDT · **Closed:** 2026-10-14 08:33:26 EDT
**Plan:** [202610/v0\_18\_0\_release.md](https://github.com/sase-org/sase--plans/blob/main/202610/v0_18_0_release.md)

## Description

visual-lane: fix the three deterministic visual failure classes (fast-startup stub vs real loader, remote rows seeded through the local loader, stale Commits description wait), regenerate only the goldens those fixes change, then prove a clean TZ=UTC full check.

## Notes

[2026-10-14T12:07:16Z · sase-1kx.2--1] PROPOSED FOLLOW-UP: Full TZ=UTC visual --check drifted 3 goldens outside Class A/B/C; 2 reproduce identically on clean HEAD 8e00f6d211 (agents_session_panel_turns_gate_90x40 14707px footer "(/) blocks" reflow — sase-1jz.3 gate-footer wait; link_rail_agents_single_link_60x30 1282px "$0 +1 more" vs "$$ implemented-by"); plan_gate_tale_decisions_maxcopy_120x40 truncation is intermittent (full run only, not targeted dirty or clean HEAD).

[2026-10-14T12:32:43Z · sase-1kx.2--1] PROPOSED FOLLOW-UP: sase tool run check 3001ace890e331c81511759a2d3b49c9 escalated to full suite (stale coverage baseline 4372 commits behind + serial-budget-exceeded from visual-file edits) and reported 26 NEW/1 FLAKY; representative nodes pass in isolation on dirty tree and clean HEAD 8e00f6d211 (axe chop bead_claim_checks leases, agent_load_tiering_production_oracle, agent_group_revival_e2e, agent_dismiss_persistence, agent_loader_agents_list_projection). Gate-reds owner is sase-1kx.1; not caused by Class A/B/C harness.

[2026-10-14T12:33:26Z · sase-1kx.2--1] Class A: patch_startup_loaders(use_real_agent_loader=True) wraps AceApp._run_agent_index_startup_prepare_and_refresh so AcePage keeps the production disk-loader path; unit test test_use_real_agent_loader_keeps_production_agent_startup passes. Class B: machine-tab tests seed remotes via FleetRowsProjection; stale_host waits for SVG "apollo: stale"; regenerated agents_tab_strip_stale_host_120x40.png. Class C: commits tests wait on _stitches_description_sentinel() from fixed_descriptor("stitches"); regenerated artifacts_stitches_filter_bar_prefilled_120x40.png and artifacts_stitches_persistent_filter_80x24.png. Best-effort spread_deck_sticky left-scrollbar wait; golden unchanged. Prior 5x targeted TZ=UTC --check of the 11 repaired tests was clean created=0 updated=0. Full TZ=UTC --check (monitor 5h734ka1khk7) 1366 passed created=0 updated=3 unchanged=1097 stale=0: the 3 drifted goldens are outside Class A/B/C; 2 reproduce identically on clean HEAD 8e00f6d211 (agents_session_panel_turns_gate_90x40 14707px footer "(/) blocks", link_rail_agents_single_link_60x30 1282px "$0 +1 more" vs "$$ implemented-by" — sase-1jz.3); plan_gate_tale_decisions_maxcopy_120x40 truncation is intermittent. epic-symbols: none. sase tool run check 3001ace890e331c81511759a2d3b49c9 failed after full-suite escalation (26 NEW/1 FLAKY) that pass in isolation on dirty tree and clean HEAD; cited sase-1kx.1. Two PROPOSED FOLLOW-UP notes recorded. Did not close parent epic.

## Dependencies

- **Blocks:** [sase-1kx.4](sase-1kx.4.md) ◐ · ⧖ 2026-10-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1kx.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kx.2.md) | [sase-1kx.2](sase-1kx.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c699972`](https://github.com/sase-org/sase/commit/c69997274d859113526852cb1c99f0767790f4df) | fix(tui): repair visual-lane loader, fleet, and stitches snapshot waits | [sase-1kx.2](sase-1kx.2.md) | 2026-10-14 08:35:03 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kx.2--1][1] | Need remaining close constraints | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1kx.2.md

<!-- sase:referenced-by:end -->
