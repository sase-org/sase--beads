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

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/agent_tabs_scope.md

<!-- sase:links:end -->

## Description

Behind the new `agent_tabs` beta flag, the Agents tab shows one agent tab at a time. A per-root tab index and ordered catalog come from the sase-core catalog. The active tab re-scopes a cached, tab-independent query result without I/O. Folds, sticky panels, and selection memory are kept per tab. The active tab persists across restarts. `[`/`]` cycle tabs, every cross-tab jump switches tabs first, and bulk confirmations name their scope. A minimal strip makes the scope visible. With the flag off, the TUI is unchanged.
