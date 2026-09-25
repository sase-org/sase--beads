# Bead: sase-198.2 — Python runtime honors explicit zero weight

[Bead Pages](../README.md) / [sase-198](README.md) / sase-198.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1n](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1n.md) · **Assignee:** `sase-198.2` · **Size:** medium
**Created:** 2026-09-25 09:49:03 EDT · **Closed:** 2026-09-25 12:22:49 EDT
**Plan:** [202609/queue\_zero\_weight.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_zero_weight.md)

## Description

py-runtime: in sase, stop Python validators, fallbacks, and inheritance paths from rejecting or dropping an explicit 0.0 queue weight, keep epic-launch monitor zero from leaking to successors, and render a w0 badge; testable with records, without the new core.

## Dependencies

- **Blocks:** [sase-198.3](sase-198.3.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-198.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-198.2.md) | [sase-198.2](sase-198.2.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4e18680`](https://github.com/sase-org/sase/commit/4e18680d3d98c3d82cef1b026edd9bf9b3590bf9) | feat: Python runtime honors explicit zero weight (sase-198.2) | [sase-198.2](sase-198.2.md) | 2026-09-25 12:20:11 EDT |
