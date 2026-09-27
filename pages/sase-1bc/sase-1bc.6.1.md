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

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1bc.6.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bc.6.1.land/README.md) | [sase-1bc.6.1](sase-1bc.6.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1bc.6.1.2][1] | Need parent epic scope for phase 2 | 1 |
| read-by | [agent:sase-1bc.6.1.5][2] | Need sub-phase statuses | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bc.6.1.2/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1bc.6.1.5/README.md

<!-- sase:referenced-by:end -->
