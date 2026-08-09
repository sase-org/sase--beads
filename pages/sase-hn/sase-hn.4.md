# Bead: sase-hn.4 — Rename the ACE TUI and configuration surface

[Bead Pages](../README.md) / [sase-hn](README.md) / sase-hn.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vu](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vu/README.md) · **Assignee:** `sase-hn.4` · **Size:** large
**Created:** 2026-08-08 13:06:11 EDT · **Closed:** 2026-08-08 21:43:18 EDT
**Plan:** [202608/patch\_and\_stitch\_terminology.md](https://github.com/sase-org/sase--plans/blob/main/202608/patch_and_stitch_terminology.md)

## Description

tui-config-surface: present Patches and stitches throughout ACE and normalize legacy keymap, config, completion, and saved-state identifiers.

## Notes

[2026-08-09T01:43:18Z · sase-hn.4] Implemented Patch/stitch ACE TUI and configuration surface rename with legacy adapters for saved tabs, keymaps, copy groups, grouping state, axe providers, and completion catalogs. Verified with just check (full-suite escalation passed), just test-visual with snapshot update and then without update, cargo test -q -p sase_core -p sase_xprompt_lsp, targeted command/keymap/help tests, terminology scans, and git diff --check in both touched repositories.

[2026-08-09T01:44:41Z · sase-hn.4] Implemented Patch/artifacts/stitches TUI surface rename with legacy compatibility; verified just check, visual snapshots, Rust core/LSP tests, terminology scans, and diff whitespace.

## Dependencies

- **Depends on:** [sase-hn.3](sase-hn.3.md) ✓ · ⧖ 2026-08-08
- **Blocks:** [sase-hn.6](sase-hn.6.md) ◐ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hn.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-hn.4.md) | [sase-hn.4](sase-hn.4.md) | 0 |
