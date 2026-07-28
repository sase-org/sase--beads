# Bead: sase-4p.2 — Phase 2: Render A Beautiful Stack In PromptInputBar

[Bead Pages](../README.md) / [sase-4p](README.md) / sase-4p.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-4p.2`
**Created:** 2026-06-15 21:37:46 UTC · **Closed:** 2026-06-15 22:38:00 UTC
**Plan:** [202606/multi\_agent\_prompt\_stack.md](https://github.com/sase-org/sase--plans/blob/main/202606/multi_agent_prompt_stack.md)

## Notes

COMMIT: a06a7e5e0

[2026-07-27T21:34:14Z · sase-a1.land] [2026-06-15T22:33:35Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Phase 2 complete: PromptInputBar renders a vertical stack of prompt panes backed by PromptStackState.

- compose()/on_mount build panes from PromptStackState; one PromptTextArea per item with generation-scoped ids (prompt-input-g{N}-{item_id}) and stable .prompt-input class; shared #prompt-completion panel stays scoped to the focused/active pane.
- Single prompts (incl. YAML frontmatter) stay one verbatim 'solo' pane; only real --- separators (canonical parser, fences/frontmatter protected) split into panes. Feedback/approve_prompt modes never split.
- Helper APIs: active_text_area(), active_text(), all_prompt_texts(), current_prompt_text() (whole-stack canonical join), load_stack_from_text(), focus_item(); _sync_state_from_widgets keeps the model in sync with live editing.
- Height rework: single-pane formula unchanged; multi-pane caps total at screen-2, active pane grows most, inactive panes compact first (_INACTIVE_PANE_MAX_ROWS=4).
- on_descendant_focus tracks the active pane; _refocus_if_needed made stack-aware so a blurred pane no longer steals focus from a sibling.
- Callers updated to stack-aware helpers: _load_prompt_into_bar + history LOAD now replace the whole stack via load_stack_from_text; _save_bar_text_as_cancelled, snippet VCS read, history refocus use the helpers.
- TCSS: stack container, solo pane (unchanged look), active/inactive multi panes (left accent bar), separator rows.
- No submission behavior change (enter still submits whole joined prompt); per-pane submit is Phase 4.
- Tests: new tests/ace/tui/widgets/test_prompt_input_bar_stack.py (13 tests) for rendering/height/rebuild/focus/mode-guards; updated keymaps_e2e + history-requests stubs. Removed the now-unused --epic-symbol pyvision whitelist for PromptStackItem/PromptStackState/split_prompt_text. just check passes.

## Dependencies

- **Depends on:** [sase-4p.1](sase-4p.1.md) ✓
- **Blocks:** [sase-4p.3](sase-4p.3.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`24ecfc4`](https://github.com/sase-org/sase/commit/24ecfc43d69ad93b98d3567289ee8540617d880f) | feat(ace): render prompt stack of panes in PromptInputBar (sase-4p.2) | [sase-4p.2](sase-4p.2.md) | 2026-06-15 22:38:38 |
