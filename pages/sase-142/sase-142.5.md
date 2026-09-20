# Bead: sase-142.5 — Make the Agents-tab row insert reachable for real arrivals and close sase-13i.4

[Bead Pages](../README.md) / [sase-142](README.md) / sase-142.5

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-142.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-142.land.md) · **Assignee:** `sase-142.5.land`
**Created:** 2026-09-20 17:09:26 EDT
**Plan:** [202609/reachable\_row\_insert.md](https://github.com/sase-org/sase--plans/blob/main/202609/reachable_row_insert.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/reachable_row_insert.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/reachable_row_insert.md

<!-- sase:links:end -->

## Description

A real agent node arriving in the @epic tribe panel on athena records display_row_insert, not display_panel_rebuild, and an apply that changes no rendered row in a panel repaints nothing in that panel. Both claims are proved by the existing frame-level harness extended to the row shapes real arrivals actually have, and re-proved by a landed-SHA soak on athena with deliberately created nodes, which closes sase-13i.4.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-142.5.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-142.5.land/README.md) | [sase-142.5](sase-142.5.md) | 0 |
