# Bead: sase-gv.3 — XPrompts tab jump

[Bead Pages](../README.md) / [sase-gv](README.md) / sase-gv.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.uo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.uo/README.md) · **Assignee:** `sase-gv.3` · **Size:** small
**Created:** 2026-08-07 09:53:02 EDT · **Closed:** 2026-08-07 11:11:52 EDT
**Plan:** [202608/admin\_center\_apostrophe\_jump.md](https://github.com/sase-org/sase--plans/blob/main/202608/admin_center_apostrophe_jump.md)

## Description

xprompts: wire the XPrompt browser's non-header rows onto the shared mixin and reserve the apostrophe in the filter-first browser input while the filter is empty.

## Notes

[2026-08-07T15:11:14Z · sase-gv.3] PROPOSED FOLLOW-UP: `just check`'s `SASE validation` step fails on this workspace with `init skills --check` wanting to overwrite 5 provider `sase_gate` skill files (chezmoi-managed, +12-2 each) — pre-existing drift unrelated to the xprompts jump wiring in this phase; needs a `sase memory init`/chezmoi sync pass with explicit user permission before `just check` can pass end to end again.

[2026-08-07T15:11:52Z · sase-gv.3] Wired XPromptBrowserPane onto PaneEntryJumpMixin: apostrophe reserved in BrowserFilterInput.on_key while filter is empty (falls through to text once non-empty), hints painted over the 3 flat item rows skipping __header__ rows via create_browser_options(hint_for=...), selection routed through _restore_highlight_and_preview, and invalidate_jump_hints applied in on_input_changed/_reload_xprompts. Verified: 9 new tests in tests/ace/tui/test_xprompt_browser_jump.py pass (hint painting skips headers, hint-selects item + updates preview, back-stack round-trip, escape cancels without closing modal, typed-filter apostrophe stays literal text, jump-mode keys don't leak into filter, filter rebuild clears stale back stack, zero-items no-op); existing 14 tests in test_xprompt_browser_load_keymap.py still pass; just lint clean (ruff/mypy/symvision/toobig); just test-visual -k xprompts passes 6/6 (1 skipped) with the refreshed config_center_xprompts_tab_120x40.png golden; full just test-scoped lane (26872 passed, 7 skipped, 0 failed). just check's SASE validation step fails on unrelated pre-existing chezmoi sase_gate skill drift (logged as a PROPOSED FOLLOW-UP note on this bead, not fixed here).

## Dependencies

- **Depends on:** [sase-gv.1](sase-gv.1.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-gv.8](sase-gv.8.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gv.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gv.3/README.md) | [sase-gv.3](sase-gv.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`64922e1`](https://github.com/sase-org/sase/commit/64922e12acefbe1e202e69fa1d8146b06b7bad2e) | feat(ace): wire XPrompts browser rows onto the shared entry-jump mixin | [sase-gv.3](sase-gv.3.md) | 2026-08-07 11:13:12 EDT |
