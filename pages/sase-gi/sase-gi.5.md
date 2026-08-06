# Bead: sase-gi.5 — NORMAL-mode J for ordered items

[Bead Pages](../README.md) / [sase-gi](README.md) / sase-gi.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ub](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ub/README.md) · **Assignee:** `sase-gi.5` · **Size:** small
**Created:** 2026-08-06 15:23:18 EDT · **Closed:** 2026-08-06 18:32:45 EDT
**Plan:** [202608/prompt\_ordered\_lists.md](https://github.com/sase-org/sase--plans/blob/main/202608/prompt_ordered_lists.md)

## Description

join: drop a pulled-up ordered marker when folding the next line up, and renumber the run the removed item left behind.

## Notes

[2026-08-06T22:32:45Z · sase-gi.5] Implemented ordered-marker drop + run renumber for NORMAL-mode J: added _normal_join_marker_dropped/_normal_join_renumber_plan hooks to VimTextArea, wired the prompt override in _prompt_text_area_actions.py folding the renumber into the join's single replacement span, added find_ordered_predecessor to _prompt_ordered_editing.py, updated _join_lines in _vim_normal_operator_exec.py to compute the renumber once per press on the final fold, and dropped the now-satisfied symvision epic-symbol allowance for strip_prompt_ordered_marker from the Justfile. Verified: 8 new tests in tests/ace/tui/widgets/test_prompt_ordered_join.py plus the updated tests/test_prompt_normal_mode_join.py case (28 total) pass; full tests/ace/tui/widgets/ + tests/test_prompt_normal_mode_join.py suite (3347 tests) passes with no regressions; just check passes (all lint gates including mypy and symvision, plus the scoped test lane, which escalated to the full suite on the Justfile change and passed).

## Dependencies

- **Depends on:** [sase-gi.3](sase-gi.3.md) ✓ · ⧖ 2026-08-06
- **Blocks:** [sase-gi.7](sase-gi.7.md) ✓ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-gi.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-gi.5/README.md) | [sase-gi.5](sase-gi.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ecce0c3`](https://github.com/sase-org/sase/commit/ecce0c3888b8381dce9fb0881a2927090d05b2e0) | feat(ace-tui): drop and renumber ordered markers on NORMAL-mode J | [sase-gi.5](sase-gi.5.md) | 2026-08-06 18:33:20 EDT |
