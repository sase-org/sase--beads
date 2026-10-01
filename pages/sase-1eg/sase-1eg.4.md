# Bead: sase-1eg.4 — Follow a link into the other pane with ctrl+w

[Bead Pages](../README.md) / [sase-1eg](README.md) / sase-1eg.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v1.md) · **Assignee:** `sase-1eg.4` · **Size:** small
**Created:** 2026-10-01 15:39:37 EDT · **Closed:** 2026-10-01 19:41:32 EDT
**Plan:** [202610/pager\_split\_panes.md](https://github.com/sase-org/sase--plans/blob/main/202610/pager_split_panes.md)

## Description

other-pane-follow: ctrl+w arms an 'other pane' follow. A painted label then opens its target in the other pane (opening a split when single) while focus stays put, and doubled ctrl+w focuses the other pane.

## Notes

[2026-10-01T23:41:32Z · sase-1eg.4] other-pane follow landed: ctrl+w arms other-pane follow (footer ^W… other pane + help rows), label opens target in other pane (stacked/beside split when single, in-place fallback toast when no room) with focus steady, doubled ctrl+w focuses other pane, attached handlers see follow, URL copy/media/unresolvable paths unchanged. Verified: 11 new pilot tests in tests/pager/test_app_other_pane.py pass, ACE modal ctrl+w test + footer/help unit tests pass, 85 neighboring pager/ACE tests pass, sase tool run check verdict pass (ruff/mypy/symvision + scoped lane).

## Dependencies

- **Depends on:** [sase-1eg.3](sase-1eg.3.md) ✓ · ⧖ 2026-10-01
- **Blocks:** [sase-1eg.5](sase-1eg.5.md) ◐ · ⧖ 2026-10-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eg.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eg.4/README.md) | [sase-1eg.4](sase-1eg.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3812f6d`](https://github.com/sase-org/sase/commit/3812f6dc1b5ee2a020b0c5006d045a0d66a5a939) | feat(pager): follow a link into the other pane with ctrl+w | [sase-1eg.4](sase-1eg.4.md) | 2026-10-01 19:43:11 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eg.3][1] | check sibling scope | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eg.3/README.md

<!-- sase:referenced-by:end -->
