# Bead: sase-1bc.6.1 — Agent tabs: tab index, active-tab scope, keys, and cross-tab navigation

[Bead Pages](../README.md) / [sase-1bc.6](sase-1bc.6.md) / sase-1bc.6.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1bc.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.6.md) · **Assignee:** `sase-1bc.6.1.land`
**Created:** 2026-09-27 13:46:05 EDT
**Plan:** [202609/agent\_tabs\_scope.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_tabs_scope.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/agent_tabs_scope.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/agent_tabs_scope.md

<!-- sase:links:end -->

## Description

Behind the new `agent_tabs` beta flag, the Agents tab shows one agent tab at a time. A per-root tab index and ordered catalog come from the sase-core catalog. The active tab re-scopes a cached, tab-independent query result without I/O. Folds, sticky panels, and selection memory are kept per tab. The active tab persists across restarts. `[`/`]` cycle tabs, every cross-tab jump switches tabs first, and bulk confirmations name their scope. A minimal strip makes the scope visible. With the flag off, the TUI is unchanged.

## Notes

[2026-09-28T00:04:35Z · sase-1bc.6.1.land] LANDING PAUSED (sase-1bc.6.1.land, master 5db68f77f2). VERIFY: all 5 phases closed with commits 8ad9637187/59f5eff166/c78eb3805f/94ed923b10/63fd6a5dfd; plan items present and phase tests green (97+50+25), but review found epic-caused flag-on defects: worker-path status overrides applied only to scoped rows; tab-index memo never hits (fresh list copy) and retains 16 rosters; tab-memory fallback uses source tab's index, focused panel never restored; emptied machine tab strands user (no latch); machine-gone toast doubles the glyph; empty first catalog skips startup selection; legacy bracket yield unbinds both tab keys; help rows shown with flag off; cross-tab back-anchor saved after switch (wrong ' target); notification pre-switch defeats failed-reveal restore; run-log/revive/Files/link-trail switch then scan _agents without fold reveal or restore; failed back-jump leaves tab switched; ,j off-tab banner-hidden candidates; marked 'N of M' miscount; custom cleanup header says 'across all tabs' for active-tab candidates; 11 agent-tabs public symbols flagged by symvision (test-only consumers). Planned as a child epic with parent_bead sase-1bc.6.1. INTEGRATE: 34fd799e98 (Node Finder ladder for notification jumps) was integrated by 63fd6a5dfd, except the redundant pre-switch (in child plan); aff4fc082f (sase-1bc.5) reuses the same canonicalize_agent_tab adapter, no duplication; 092fb8bf10 node-finder release covers off-tab labels (stored in rows); 42bb50a80c/74d1ab8e1a/ee2c447cfd/c941ade911 do not touch #agents-header or tab state; c8a7a5ed3c keymaps add no bracket conflicts. FOLLOW-UPS: usage_windows symvision pragmas (6.1.1#1, 6.1.2#1, 6.1.3#1) already tracked by sase-1bj, not +1'd (no local reproduction); test_agent_completion 9 failures (6.1.2#2) and 2 directive-completion absence tests (6.1.2#3) already recorded as DISCOVERED ISSUE notes #1/#2 on sase-1bc (caused by 372ecc97c3, sase-1bc.4); header-panel scroll failure (6.1.2#3, 6.1.4#1) +1'd on sase-1b8; timezone guard (6.1.2#5) +1'd on sase-1bp; test_keymaps_e2e::test_remapped_navigation_key (6.1.2#4) declined: 12/12 pass on rerun, no failure output to file as a flake; symvision _segment_section_identity (6.1.4#1, 6.1.5#1) declined: fixed by 34fd799e98; live flag-on screenshot deferral (6.1.3#2) declined: delivered by 6.1.5 (/tmp/scope_honesty_*.png). epic-symbols: none for sase-1bc.6.1.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.6.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1bc.6.1.land.md) | [sase-1bc.6.1](sase-1bc.6.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bc.6.1.2][1] | Need parent epic scope for phase 2 | 1 |
| read-by | [agent:sase-1bc.6.1.5][2] | Need sub-phase statuses | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bc.6.1.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bc.6.1.5/README.md

<!-- sase:referenced-by:end -->
