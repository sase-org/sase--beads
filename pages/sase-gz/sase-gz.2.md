# Bead: sase-gz.2 — Icon resolution chain and configuration

[Bead Pages](../README.md) / [sase-gz](README.md) / sase-gz.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ui.w1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ui.w1/README.md) · **Assignee:** `sase-gz.2` · **Size:** medium
**Created:** 2026-08-07 10:28:44 EDT · **Closed:** 2026-08-07 11:14:17 EDT
**Plan:** [202608/notification\_tab\_icons.md](https://github.com/sase-org/sase--plans/blob/main/202608/notification_tab_icons.md)

## Description

icon-chain: add `resolve_notification_tab_icon` to the tab-style module with its four-rung resolution chain, the built-in key and kind glyph tables, the `ace.notification_tabs.*.icon` setting, its JSON-schema entry, and the bundled defaults.

## Notes

[2026-08-07T15:13:46Z · sase-gz.2] PROPOSED FOLLOW-UP: sase_gate skill deploy is stale — `sase validate` fails `init skills --check` on a clean master tree with 5 provider sase_gate/SKILL.md files needing overwrite (+12 −2 each); a `sase skill init` deploy is owed from a clean tree.

[2026-08-07T15:14:17Z · sase-gz.2] icon-chain landed in the working tree. Added _BUILTIN_TAB_ICONS (⚑ ✖ ◈ ✉ ☾ ⊘), _KIND_TAB_ICONS (the 7 core kinds), the '•' last resort, and resolve_notification_tab_icon() implementing the 4-rung chain (config > tab.icon > builtin key > kind > last resort), exported in __all__ and reusing _notification_tab_config_key so config keys stay 'snoozed'/'muted'. Replaced _configured_tab_colors_for_token with _configured_tab_styles_for_token, one cached parse returning color+icon per key. Configured/declared icons are sanitized through validate_icon (one definition of a legal icon) inside try/except GateError, plus ACE's own cell_len>2 guard. Added NotificationTagTab.icon, populated from the core tab via getattr so pre-icon cores still work. Added icon to all 6 ace.notification_tabs entries in default_config.yml and an icon field (string, maxLength 32, default '') to sase.schema.json. Verified: 84 tests in test_notification_tab_style.py / test_config_schema_notification_tabs.py / test_notification_indicator.py pass, including one case per rung, junk-config and junk-stored fallthrough, empty-string reset, the width guard, and a parity test asserting _BUILTIN_TAB_ICONS matches the bundled default_config.yml icons. Confirmed every bundled glyph is cell_len 1. just check: all lint gates green; just test-scoped: 26891 passed, 7 skipped. Added --epic-symbol 'sase-gz.4(resolve_notification_tab_icon)' to the Justfile symvision invocation since the render phase is its first consumer; sase-gz.4 must drop that entry. The only just check failure is SASE validation's 'init skills --check', which reproduces identically on a stashed clean master tree and is unrelated (noted as a follow-up). Work is uncommitted in the workspace.

## Dependencies

- **Blocks:** [sase-gz.4](sase-gz.4.md) ◐ · ⧖ 2026-08-07
- **Blocks:** [sase-gz.5](sase-gz.5.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gz.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gz.2/README.md) | [sase-gz.2](sase-gz.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`72148dc`](https://github.com/sase-org/sase/commit/72148dcab071a6f4ee1bc69832b1d96481a22ef0) | feat(ace): resolve notification tab icons through a four-rung chain | [sase-gz.2](sase-gz.2.md) | 2026-08-07 11:15:20 EDT |
