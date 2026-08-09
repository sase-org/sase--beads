# Bead: sase-hp.6 — Help modal, footer, and documentation

[Bead Pages](../README.md) / [sase-hp](README.md) / sase-hp.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vy](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vy/README.md) · **Assignee:** `sase-hp.6` · **Size:** small
**Created:** 2026-08-08 15:52:36 EDT · **Closed:** 2026-08-08 19:28:22 EDT
**Plan:** [202608/xprompt\_target\_mode.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_target_mode.md)

## Description

docs: bring the `?` help popup, the conditional keybinding footer, and the ACE / xprompt documentation in line with the new targeting keys and save flow.

## Notes

[2026-08-08T23:23:48Z · sase-hp.6] PROPOSED FOLLOW-UP: Skipped wiring a save-key row into keybinding_footer.py (the app-level bottom bar) despite the epic plan naming that file. Verified via prompt_stack_targeted_dirty_120x40.png and CSS (both #keybinding-footer and PromptInputBar are dock:bottom siblings mounted directly on the App) that the bottom KeybindingFooter is visually covered by the PromptInputBar while composing/targeting a prompt, so a footer-side keymap row would be dead/unreachable UI. The equivalent affordance already ships where it is actually visible: PromptInputBar.insert_mode_subtitle()/normal_mode_subtitle() show a `[^G w] save <reference>` hint (added in the visual phase). If this judgment call is wrong, the fix is to add a _compute_prompt_target_bindings()-style method plus a call site in _display_detail_footer.py.

[2026-08-08T23:24:23Z · sase-hp.6] PROPOSED FOLLOW-UP: tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py::test_prompt_artifact_ref_highlight_png_snapshot fails on a clean master checkout (verified via git stash before touching any files in this phase) with a small pixel-diff (4399/1520532 px, 0.29%) against tests/ace/tui/visual/snapshots/png/prompt_artifact_ref_highlight_120x40.png. Unrelated to sase-hp; looks like renderer/font drift on this golden. Needs triage: either the golden needs a refresh or diff tolerance needs adjusting.

[2026-08-08T23:24:49Z · sase-hp.6] PROPOSED FOLLOW-UP: Consider adding a sase/memory/glossary.md entry for "xprompt target" / "targeting" (the prompt-input-bar state introduced by epic sase-hp: a bar bound to a specific xprompt/memory-note/skill-source file, with a canonical reference chip, clean/dirty/read-only/stale visual states, a gw/Ctrl+G w save key, and chezmoi-aware write-path + follow-up-action semantics). Not added by this docs phase since memory files require explicit user permission.

[2026-08-08T23:28:22Z · sase-hp.6] Brought the ? help popup (PROMPT_INPUT_SECTION: added #@ Ctrl+O 'edit definition here' and gw/Ctrl+G w 'save to targeted xprompt' rows) and docs/ace.md + docs/xprompt.md in line with the sase-hp targeting/save-flow phases (target, surfaces, menu, followup, visual). Fixed stale Admin Center XPrompts-tab doc (Enter now targets into the prompt bar, not $EDITOR; Ctrl+I is inline-expand; added the E/external-editor row) and the Prompt Stacks Enter-key row. Added a new docs/ace.md#editing-an-existing-xprompt-from-the-tui section covering entry points, visual chip states, the target-aware Enter chooser, gw, the chezmoi write-path redirect, and PostWriteActionsModal follow-up actions (commit/push, scoped chezmoi apply, sase memory init, sase skill init), plus matching cross-links from docs/xprompt.md's Skill Field and Memory Field sections. Investigated the plan's keybinding_footer.py line item and determined (via the prompt_stack_targeted_dirty golden + dock:bottom CSS) that the app-level KeybindingFooter is visually covered by PromptInputBar while targeting, so the save-key affordance already lives where it's visible (PromptInputBar's own insert/normal-mode subtitle, shipped in the visual phase) rather than in that file; recorded as a PROPOSED FOLLOW-UP for review. Regenerated tests/ace/tui/visual/snapshots/png/help_keymaps_changespecs_120x40.png for the two new help-modal rows. Verified: just check (fmt/lint/SASE validation/scoped tests) passes clean; just test-visual passes except one pre-existing, unrelated failure (test_prompt_artifact_ref_highlight_png_snapshot, reproduces on a clean master checkout) noted as a separate PROPOSED FOLLOW-UP. Also proposed a PROPOSED FOLLOW-UP for a possible glossary entry on 'xprompt target'.

[2026-08-08T23:29:44Z · sase-hp.6] Added help-modal rows (Select XPrompt Ctrl+O, gw save-to-target), fixed stale Admin Center XPrompts-tab docs (Enter targets/loads not $EDITOR, added E row, corrected Ctrl+I), fixed Prompt Stacks Enter row, added docs/ace.md 'Editing an Existing XPrompt from the TUI' section, cross-linked from docs/xprompt.md, regenerated affected PNG golden. just check passes; just test-visual passes except one pre-existing unrelated failure.

## Dependencies

- **Depends on:** [sase-hp.2](sase-hp.2.md) ✓ · ⧖ 2026-08-08
- **Depends on:** [sase-hp.3](sase-hp.3.md) ✓ · ⧖ 2026-08-08
- **Depends on:** [sase-hp.4](sase-hp.4.md) ✓ · ⧖ 2026-08-08
- **Depends on:** [sase-hp.5](sase-hp.5.md) ✓ · ⧖ 2026-08-08
- **Blocks:** [sase-hp.7](sase-hp.7.md) ✓ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hp.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hp.6/README.md) | [sase-hp.6](sase-hp.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`65f82cc`](https://github.com/sase-org/sase/commit/65f82ccd9f52946f2633b7aa0d986cefc7732858) | docs(ace): document xprompt targeting/save-flow entry points and fix stale help text | [sase-hp.6](sase-hp.6.md) | 2026-08-08 19:32:01 EDT |
