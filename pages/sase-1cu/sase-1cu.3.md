# Bead: sase-1cu.3 — Snippet location-first flow and Ctrl+G Ctrl+T alias

[Bead Pages](../README.md) / [sase-1cu](README.md) / sase-1cu.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u8.md) · **Assignee:** `sase-1cu.3` · **Size:** medium
**Created:** 2026-09-29 18:58:49 EDT · **Closed:** 2026-09-29 20:51:50 EDT
**Plan:** [202609/save\_location\_picker.md](https://github.com/sase-org/sase--plans/blob/main/202609/save_location_picker.md)

## Description

snippet-flow: add the Ctrl+G Ctrl+T alias, route the snippet request through the picker, lock the destination in SnippetNameModal with arrows moving matches and Shift+Tab going back, update tests, snapshots, help, and snippet docs.

## Notes

[2026-09-30T00:51:24Z · sase-1cu.3] PROPOSED FOLLOW-UP: just check is red on clean base too — _lint-patch-stitch-terminology flags sase-core fixture at_bearing_notes.jsonl and symvision flags private imports _kitty_graphics_support/_roster_for_issue; both reproduce identically with this phase stashed

[2026-09-30T00:51:50Z · sase-1cu.3] Snippet location-first flow done: Ctrl+G Ctrl+T alias added (^G prefix verified to run before Ctrl+T completion); picker pushed synchronously with off-thread loads, type-ahead, fallback-notice, and origin-lost handling; SnippetNameModal destination locked with match navigation, Shift+Tab round trip preserving typed text, stepper header and Saving-to panel. Verified: 8 new flow tests + updated modal/save/hint/help suites all pass, whole-repo ruff/mypy/fmt/keep-sorted/test-waits/flags green, snippet PNG goldens regenerated and visually inspected, visual check-only clean. just check as a whole stays red only on two pre-existing base failures (patch-stitch terminology gate, symvision private imports), recorded as follow-up; removed 3 stale sase-1cu epic-symbol entries, kept xprompt_location_choices for open sibling .2. default_config.yml needs no change (prompt ^G table is code-driven). No sase-core changes.

## Dependencies

- **Depends on:** [sase-1cu.1](sase-1cu.1.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cu.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cu.3/README.md) | [sase-1cu.3](sase-1cu.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c44ec32`](https://github.com/sase-org/sase/commit/c44ec32abe440ad11632ead7179c0f1f0c394e7b) | feat(ace): snippet location-first save flow with picker and rename defaults | [sase-1cu.3](sase-1cu.3.md) | 2026-09-29 20:54:09 EDT |
