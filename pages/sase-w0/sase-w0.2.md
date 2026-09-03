# Bead: sase-w0.2 — One list, domain sections, and the scope filter

[Bead Pages](../README.md) / [sase-w0](README.md) / sase-w0.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.5.md) · **Assignee:** `sase-w0.2` · **Size:** large
**Created:** 2026-09-03 06:53:42 EDT · **Closed:** 2026-09-03 17:10:06 EDT
**Plan:** [202609/unified\_updates\_tab\_1.md](https://github.com/sase-org/sase--plans/blob/main/202609/unified_updates_tab_1.md)

## Description

list: replace the tab strip, ContentSwitcher, and two OptionList/detail pairs with one scope strip and one master/detail surface; add scope cycling on the existing bracket keys, kind-dispatched detail, one selection guard and one bookmark, a widened filter haystack, unified widget ids and CSS, and update the pane tests, the TUI scale bench, and the PNG snapshot suite.

## Notes

[2026-09-03T21:06:13Z · sase-w0.2--1] PROPOSED FOLLOW-UP: just check's scoped lane escalated to the full suite (core-identity-changed). After the fmt, flag task-type snapshot, and stub-loader uv_tool getattr fixes, remaining full-suite failures look unrelated to this phase: August vs September prompt archive path, bead note CLI SystemExit 2, external PR mirror table output, residual freeze soak, and two startup-stopwatch tests. Land should treat them as pre-existing unless they reproduce on an unchanged tree.

PROPOSED FOLLOW-UP: jump-hint allocation at n=2000 is still hundreds of ms (not gated; filter/j-press p95 stay under 16ms). Recorded TUI baseline JSON was left for the docs phase.

[2026-09-03T21:10:06Z · sase-w0.2--1] Auto-closed by `sase stitch create` after create_commit landed 4c1c7b24e ("feat(ace): merge Updates tab into one scoped inventory list"). No verification is implied by this note. Reopen with `sase bead open sase-w0.2`, or pass `-B|--do-not-close-bead` on mid-flight commits.

## Dependencies

- **Depends on:** [sase-w0.1](sase-w0.1.md) ✓ · ⧖ 2026-09-03
- **Blocks:** [sase-w0.3](sase-w0.3.md) ◐ · ⧖ 2026-09-03
- **Blocks:** [sase-w0.4](sase-w0.4.md) ✓ · ⧖ 2026-09-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-w0.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-w0.2.md) | [sase-w0.2](sase-w0.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4c1c7b2`](https://github.com/sase-org/sase/commit/4c1c7b24ef396eef3973edaba33c0c9ce5ecc6d6) | feat(ace): merge Updates tab into one scoped inventory list | [sase-w0.2](sase-w0.2.md) | 2026-09-03 17:08:59 EDT |
