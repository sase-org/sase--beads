# Bead: sase-11y.10.1.7 — Finish the service-host sunset leftovers found at landing

[Bead Pages](../README.md) / [sase-11y.10.1](sase-11y.10.1.md) / sase-11y.10.1.7

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.10.1.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.10.1.land.md) · **Assignee:** `sase-11y.10.1.7.land`
**Created:** 2026-09-21 03:59:12 EDT
**Plan:** [202609/service\_host\_sunset\_finish.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset_finish.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/service_host_sunset_finish.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/service_host_sunset_finish.md

<!-- sase:links:end -->

## Description

No code path outside the sase service host starts the scheduler, nothing reads the retired AXE desired-state marker, `sase scheduler` offers no option it ignores, the Services-tab collector carries no permanently-empty legacy fields, and every non-blog doc describes the shipped service host, scheduler alias, and Services tab.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.10.1.7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.10.1.7.land/README.md) | [sase-11y.10.1.7](sase-11y.10.1.7.md) | 0 |
