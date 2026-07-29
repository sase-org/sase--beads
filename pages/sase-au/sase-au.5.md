# Bead: sase-au.5 — Zoom into one xprompt with a focus picker, scope chip, and keys

[Bead Pages](../README.md) / [sase-au](README.md) / sase-au.5

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-au.5` · **Size:** medium
**Created:** 2026-07-29 16:26:35 UTC · **Closed:** 2026-07-29 17:47:25 UTC
**Plan:** [202607/xprompt\_statistics.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_statistics.md)

## Description

tui-focus: add the xprompt focus picker modal, the XPrompt scope chip, the focus/clear keymaps and their configuration surfaces, the focused body rendering, and the contextual help updates.

## Notes

[2026-07-29T17:47:25Z · sase-au.5] Implemented the XPrompt focus picker, x/X keymap/config surfaces, scope chip, focused dashboards for all four groupings, stale-worker guard, contextual help/methodology, and regression coverage. Verified with just install; COLUMNS=200 just check (all lint/validation gates and 23,748 tests passed); 171 focused Statistics/keymap/config tests; Statistics PNG snapshots including reviewed help golden.

[2026-07-29T17:47:59Z · sase-au.5] Verified COLUMNS=200 just check passed all formatting, lint, validation, plan, PNG snapshot, and 23,748 test checks; focused XPrompt picker, scope, grouping renders, stale-worker guard, keymaps, help, and regression coverage are complete.

## Dependencies

- **Depends on:** [sase-au.4](sase-au.4.md) ✓
- **Blocks:** [sase-au.6](sase-au.6.md) ✓
