# Bead: sase-1fv.5 — Wire the existing path into the mini-macro flow

[Bead Pages](../README.md) / [sase-1fv](README.md) / sase-1fv.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0w7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0w7.md) · **Assignee:** `sase-1fv.5` · **Size:** medium
**Created:** 2026-10-04 06:33:06 EDT · **Closed:** 2026-10-04 11:51:59 EDT
**Plan:** [202610/existing\_macro\_snippet\_editing.md](https://github.com/sase-org/sase--plans/blob/main/202610/existing_macro_snippet_editing.md)

## Description

wire-macro-existing: connect the `e` row, the finder, in-place edits, and the read-only override detour into `_MiniMacroLocationFlow`. Add replace-draft and dirty-guard semantics for an already-open pane, refresh the hint label, and update the shared picker docs and the mini-macro docs.

## Notes

[2026-10-04T15:35:14Z · sase-1fv.5--1] PROPOSED FOLLOW-UP: just _lint-symvision unused-public in src/sase/axe/runner_kill_provenance.py (KillProvenance, classify_runner_kill, format_kill_classification, oom_kill_evidence, reset_oom_baseline) — clean-tree, tracked by sase-1g0 (related sase-1c1 / sase-1ay); this phase does not touch that file

[2026-10-04T15:51:59Z · sase-1fv.5--2] Wired e-row, existing finder, in-place edit, and read-only override into MiniMacroLocationFlow (extracted from the pane mixin). replace_draft keeps focus-restore; dirty open panes go through confirm_discard_dirty_auxiliary. Hint label is now 'new / edit mini-macro…'; picker/finder docs and gx keymap rows updated. 63 targeted tests passed (location flow, replace_draft lifecycle, g-prefix hints, picker+finder PNG goldens). Re-keyed Justfile epic-symbols off this phase onto sase-1fv.6(snippet_existing_entries). just _lint-symvision still fails on unused-public KillProvenance/classify_runner_kill/format_kill_classification/oom_kill_evidence/reset_oom_baseline in src/sase/axe/runner_kill_provenance.py — clean-tree, tracked by sase-1g0; this phase does not touch that file.

## Dependencies

- **Depends on:** [sase-1fv.3](sase-1fv.3.md) ✓ · ⧖ 2026-10-04
- **Depends on:** [sase-1fv.4](sase-1fv.4.md) ✓ · ⧖ 2026-10-04
- **Blocks:** [sase-1fv.6](sase-1fv.6.md) ✓ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1fv.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1fv.5.md) | [sase-1fv.5](sase-1fv.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d6e856f`](https://github.com/sase-org/sase/commit/d6e856f4d9469fa2fb7cd4b9cc055d44abbcb5a9) | feat(tui): wire existing-definition path into mini-macro flow | [sase-1fv.5](sase-1fv.5.md) | 2026-10-04 11:53:53 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1fv.3][1] | Need later phase id to re-key ExistingRowSpec epic-symbol | 2 |
| read-by | [agent:sase-1fv.4][2] | Need the open phase that will consume the finder modal and macro entry builder | 1 |
| read-by | [agent:sase-1fv.5--2][3] | Need the phase scope and design file | 1 |
| read-by | [agent:toobig-6y.test_detach_scope.0][4] | Need the phase close claim for leftover epic-symbol entries | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1fv.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1fv.4/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1fv.5.md
[4]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.toobig-6y.test_detach_scope.0/README.md

<!-- sase:referenced-by:end -->
