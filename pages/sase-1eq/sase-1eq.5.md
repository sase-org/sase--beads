# Bead: sase-1eq.5 — TUI macro surfaces and goldens

[Bead Pages](../README.md) / [sase-1eq](README.md) / sase-1eq.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v4.md) · **Assignee:** `sase-1eq.5` · **Size:** large
**Created:** 2026-10-02 06:51:26 EDT · **Closed:** 2026-10-04 23:24:43 EDT
**Plan:** [202610/xprompts\_to\_macros.md](https://github.com/sase-org/sase--plans/blob/main/202610/xprompts_to_macros.md)

## Description

tui: rename TUI modules, identifiers, CSS, copy, keymap actions, and Admin Center ids. Apply the raw-prompt wording for the agent prompt tab and headings, and re-baseline the PNG goldens whose pixels change.

## Notes

[2026-10-04T21:00:53Z · 50--c] -d 🔒 sase-1eq-prompt-precedence-note.md

[2026-10-05T03:26:08Z · sase-1eq.5.1.land] Verified by sase-1eq.5.1.land when the nested close auto-closed this phase: child epic sase-1eq.5.1 implemented this entire tui phase. TUI modules, identifiers, CSS, copy, keymap actions (focus_macro, clear_macro_focus, start_last_vcs_macro_in_editor, with flag-gated legacy aliases), and the Admin Center sub-tab and Statistics view ids (macros, with unconditional xprompts readers) now use macro spellings. The preview tab reads RAW PROMPT and the headings read AGENT RAW PROMPT. PNG goldens carry macro names after a full inspected tui-goldens run. The terminology guard covers the TUI trees and passes at HEAD after the land agent's allowlist integration fix. The remaining wires are owned by sase-1eq.10 (pointer note recorded there). See the sase-1eq.5.1 close note for the full verification and follow-up triage. Containing epic sase-1eq is left to its land agent.

## Attachments

- 🔒 sase-1eq-prompt-precedence-note.md · text/markdown · 1.05176 KiB (private attachment)

## Dependencies

- **Blocks:** [sase-1eq.10](sase-1eq.10.md) ◐ · ⧖ 2026-10-02
- **Depends on:** [sase-1eq.4](sase-1eq.4.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.5.md) | [sase-1eq.5](sase-1eq.5.md) | 0 |
