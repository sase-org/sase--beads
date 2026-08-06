# Bead: sase-gi.3 — NORMAL-mode o and O for ordered items

[Bead Pages](../README.md) / [sase-gi](README.md) / sase-gi.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ub](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ub/README.md) · **Assignee:** `sase-gi.3` · **Size:** medium
**Created:** 2026-08-06 15:23:02 EDT · **Closed:** 2026-08-06 17:49:01 EDT
**Plan:** [202608/prompt\_ordered\_lists.md](https://github.com/sase-org/sase--plans/blob/main/202608/prompt_ordered_lists.md)

## Description

openline: add an optional planned-edit hook to the vim open-line commands so prompt panes open a correctly numbered ordered sibling below or above, renumber the run, and keep dot-repeat recomputing at the destination.

## Notes

[2026-08-06T21:49:01Z · sase-gi.3] NORMAL-mode o/O now open correctly numbered ordered siblings. Added _normal_open_line_plan/_apply_normal_open_line_plan host hooks on VimTextArea (default None -> bare VimTextArea and SingleLineVimTextArea behavior unchanged), consulted from the o/O branches in _vim_normal_editing before the existing string hooks and after entering INSERT mode; PromptTextArea overrides them with the new plan_ordered_open_line planner (one TextEdit = one undo checkpoint, run renumbered, hyphen path byte-identical when the planner declines). Also added normalize_prompt_ordered_replay_text so dot-repeat does not replay a typed ordered marker on top of a structurally supplied one, and a style_override parameter on plan_ordered_list_edit: without it, 'O' above a run's first item duplicates its number and the post-edit lines read as Prettier's 1./1. repeat convention, which would have collapsed a whole sequential run. Verified: new tests/ace/tui/widgets/test_prompt_ordered_open_line_editing.py (33 cases: o/O on marker rows, continuation lines, nested runs, ) delimiters, hyphen/plain fallthrough, run renumbering across blank lines, repeat-style preservation, 9.->10. owned-block width shift, cursor correctness when renumbering narrows lines above it, oversized-run degradation, undo-as-one-checkpoint for o and O, three dot-repeat cases, bare VimTextArea staying bare, and three prettier formatter-fixed-point cases) plus two new style_override unit tests in test_prompt_ordered_renumber.py; existing bullet/ordered/join suites unchanged. just check passed (413/2363 scoped files) and just check-full passed end to end.

## Dependencies

- **Depends on:** [sase-gi.2](sase-gi.2.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-gi.5](sase-gi.5.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-gi.7](sase-gi.7.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gi.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gi.3/README.md) | [sase-gi.3](sase-gi.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a3108ef`](https://github.com/sase-org/sase/commit/a3108ef4f2950f9d7fb1d481d0704471d6317d20) | feat(ace-tui): open numbered ordered siblings on NORMAL-mode o and O | [sase-gi.3](sase-gi.3.md) | 2026-08-06 17:50:10 EDT |
