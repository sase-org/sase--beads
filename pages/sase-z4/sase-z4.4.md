# Bead: sase-z4.4 — Separate capacity from counts and render quiet weight badges

[Bead Pages](../README.md) / [sase-z4](README.md) / sase-z4.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0i5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0i5.md) · **Assignee:** `sase-z4.4` · **Size:** medium
**Created:** 2026-09-09 20:51:18 EDT · **Closed:** 2026-09-10 01:22:10 EDT
**Plan:** [202609/weighted\_queue\_capacity.md](https://github.com/sase-org/sase--plans/blob/main/202609/weighted_queue_capacity.md)

## Description

capacity-ux: feed shared capacity into the TUI and CLI, render global usage before status brackets, add non-default agent weight badges and queue explanations, and verify refresh and visual behavior.

## Notes

[2026-09-10T05:22:10Z · sase-z4.4] Implemented weighted runner-capacity UX, ran focused capacity/list/detail tests (122 passed), and ran just check successfully; epic-symbols reported no leftovers.

## Dependencies

- **Depends on:** [sase-z4.3](sase-z4.3.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-z4.5](sase-z4.5.md) ◐ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z4.4/README.md) | [sase-z4.4](sase-z4.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`81064c1`](https://github.com/sase-org/sase/commit/81064c144a7ef289d0c9080a7565a6f62ecae0f7) | feat(tui): show weighted runner capacity | [sase-z4.4](sase-z4.4.md) | 2026-09-10 01:25:48 EDT |
