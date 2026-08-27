# Bead: sase-ud.13.1.3.1 — Retire the notification and family status overrides

[Bead Pages](../README.md) / [sase-ud.13.1.3](sase-ud.13.1.3.md) / sase-ud.13.1.3.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ud.13.1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ud.13.1.3.md) · **Assignee:** `sase-ud.13.1.3.1.land`
**Created:** 2026-08-27 11:52:51 EDT
**Plan:** [202608/status\_strip.md](https://github.com/sase-org/sase--plans/blob/main/202608/status_strip.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202608/status_strip.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202608/status_strip.md

<!-- sase:links:end -->

## Description

A plan or question status reaches the Agents tab from exactly one place — the gate shell's own recorded start/stop pair and declared accent. The notification-driven pending-plan and question overrides, the `_agent_pre_question_status` map, the `_agent_status_overrides` re-export facade, the synthetic planner children, and the timestamp-reconstruction passes in `apply_status_overrides` are gone, with every surviving symbol kept for a stated reason rather than by omission.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ud.13.1.3.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ud.13.1.3.1.land/README.md) | [sase-ud.13.1.3.1](sase-ud.13.1.3.1.md) | 0 |
