# Bead: sase-p3.6 — Builtin task types and the \`sase bead task-type\` command group

[Bead Pages](../README.md) / [sase-p3](README.md) / sase-p3.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05c.md) · **Assignee:** `sase-p3.6` · **Size:** medium
**Created:** 2026-08-17 18:50:05 EDT · **Closed:** 2026-08-17 23:43:23 EDT
**Plan:** [202608/task\_bead\_types.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_bead_types.md)

## Description

builtins: author the bug, ci, feature, flake, and memory builtin specs and expose the catalog through a `sase bead task-type` group.

## Notes

[2026-08-18T03:42:26Z · sase-p3.6] PROPOSED FOLLOW-UP: stale --epic-symbol entries for closed sase-p1.7, sase-p3.11, and sase-p4.3 turn just check red — re-key to still-open parent epics or drop once those symbols have non-test consumers

[2026-08-18T03:42:43Z · sase-p3.6] PROPOSED FOLLOW-UP: tools/check_feature_flags fails: live flag bead sase-pa has no definition (key epic_resume_gate)

[2026-08-18T03:42:59Z · sase-p3.6] PROPOSED FOLLOW-UP: full-suite tests/test_keymaps_display_help.py::test_help_modal_lists_prompt_pane_focus_and_reorder failed asserting Ctrl+] jump-to-xprompt help — not caused by this phase

[2026-08-18T03:43:23Z · sase-p3.6] Authored bug/ci/feature/flake/memory builtin specs (Rust-validated, 1-cell glyphs, D9 accents) and sase bead task-type list/show with default-list, -a/--all, -j/--json. Verified live list/show, plugin shadowing of builtin slugs is rejected, completion snapshot updated, and 87 targeted tests passed. just check remains blocked by pre-existing stale --epic-symbol entries and flag bead sase-pa; this phase has no leftover --epic-symbol entries.

[2026-08-18T03:44:24Z · sase-p3.6] Authored bug/ci/feature/flake/memory builtin specs (Rust-validated, 1-cell glyphs, D9 accents) and sase bead task-type list/show with default-list, -a/--all, -j/--json. Verified live list/show, plugin shadowing of builtin slugs is rejected, completion snapshot updated, and 87 targeted tests passed. This phase has no leftover --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-p3.10](sase-p3.10.md) ✓ · ⧖ 2026-08-17
- **Depends on:** [sase-p3.5](sase-p3.5.md) ✓ · ⧖ 2026-08-17
- **Blocks:** [sase-p3.7](sase-p3.7.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p3.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p3.6/README.md) | [sase-p3.6](sase-p3.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0c4be02`](https://github.com/sase-org/sase/commit/0c4be02152b9c66b91c29c880c74c9bb50da2410) | feat(task-types): add builtin catalog and \`sase bead task-type\` | [sase-p3.6](sase-p3.6.md) | 2026-08-17 23:45:05 EDT |
