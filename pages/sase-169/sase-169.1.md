# Bead: sase-169.1 — Stop unmarked tests from blocking full inventories

[Bead Pages](../README.md) / [sase-169](README.md) / sase-169.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1i](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1i.md) · **Assignee:** `sase-169.1` · **Size:** small
**Created:** 2026-09-22 10:17:58 EDT · **Closed:** 2026-09-22 12:19:52 EDT
**Plan:** [202609/fix\_tui\_screenshots\_never\_fail.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_tui_screenshots_never_fail.md)

## Description

marker-evidence: make the capture plugin ignore marker-based deselection of tests that cannot produce PNG goldens. Mark the stray startup-regression module as visual and add a static guard so no test module under a visual root misses the marker.

## Dependencies

- **Blocks:** [sase-169.5](sase-169.5.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-169.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-169.1.md) | [sase-169.1](sase-169.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7c763a2`](https://github.com/sase-org/sase/commit/7c763a2e7b0173c2ffdd8f17d79c8f9f7a96d473) | test(visual): ignore non-visual deselection in capture inventory | [sase-169.1](sase-169.1.md) | 2026-09-22 10:54:16 EDT |
