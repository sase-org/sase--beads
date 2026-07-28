# Bead: sase-28.4 — Phase 4: Typed Cursor Detection And #@ Selection Parity

[Bead Pages](../README.md) / [sase-28](README.md) / sase-28.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-28.4`
**Created:** 2026-05-07 04:13:47 UTC
**Plan:** [202605/tui\_xprompt\_argument\_assist.md](https://github.com/sase-org/sase--plans/blob/main/202605/tui_xprompt_argument_assist.md)

## Notes

Implemented Phase 4 typed xprompt argument hint detection and #@ selection parity. Added pure cursor detection for colon/paren argument positions, HITL suffixes, slash/__ aliases, comma progress, project-context catalog lookup, snippet-tabstop skip, and broad-case rejection. Wired prompt refresh to cached assist entries and #@ insertion to the accepted hint path. Verification: just install; .venv/bin/pytest tests/ace/tui/widgets/test_xprompt_arg_assist.py tests/ace/tui/widgets/test_xprompt_arg_hints.py tests/ace/tui/widgets/test_prompt_file_history_completion.py; just check.

## Dependencies

- **Depends on:** [sase-28.3](sase-28.3.md) ✓
- **Blocks:** [sase-28.5](sase-28.5.md) ✓
