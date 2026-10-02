# Bead: sase-1es.6 — Swap the Static body for a Line-API ScrollView

[Bead Pages](../README.md) / [sase-1es](README.md) / sase-1es.6

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v9.md) · **Assignee:** `sase-1es.6` · **Size:** large
**Created:** 2026-10-02 08:37:52 EDT
**Plan:** [202610/pager\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202610/pager_performance.md)

## Description

virtual-body-widget: replace the one-giant-Static body with a ScrollView that renders only visible rows from the line model through a bounded strip cache, split invalidation into paint versus layout, and keep every PNG golden unchanged.

## Dependencies

- **Depends on:** [sase-1es.5](sase-1es.5.md) ◐ · ⧖ 2026-10-02
- **Blocks:** [sase-1es.7](sase-1es.7.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1es.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1es.6/README.md) | [sase-1es.6](sase-1es.6.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:0vd][1] | Check phase deps and notes to assess conflict with three-pane split work | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.0vd/README.md

<!-- sase:referenced-by:end -->
