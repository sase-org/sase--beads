# Bead: sase-j9.2 — Give \`H\` a hinted fold collapse on a selected tribe panel

[Bead Pages](../README.md) / [sase-j9](README.md) / sase-j9.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.xo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.xo/README.md) · **Assignee:** `sase-j9.2` · **Size:** medium
**Created:** 2026-08-10 17:21:17 EDT · **Closed:** 2026-08-10 20:02:17 EDT
**Plan:** [202608/agents\_panel\_fold\_sweep.md](https://github.com/sase-org/sase--plans/blob/main/202608/agents_panel_fold_sweep.md)

## Description

hint: replace the whole-panel `H` collapse ladder with a collapse-intent fold hint mode — the `L` hint affordance restricted to folds that are currently expanded, collapsing the picked fold instead of toggling it. Retire the now-dead panel-ladder resolvers, and resync the footer, help modal, keymap labels, and docs.

## Notes

[2026-08-11T00:01:43Z · sase-j9.2] PROPOSED FOLLOW-UP: `just check`'s symvision gate is broken repo-wide by a stale `--epic-symbol "sase-j3(SnippetTriggerMatch)"` entry in Justfile:306 — bead sase-j3 is closed. Remove the entry and privatize/delete `SnippetTriggerMatch` in src/sase/xprompt/snippet_targets.py (confirmed via direct symvision invocation without the whitelist: it is the only remaining finding).

[2026-08-11T00:01:58Z · sase-j9.2] PROPOSED FOLLOW-UP: tests/test_keymaps_registry_loading.py::test_stitches_action_override_wins_over_legacy_commits_alias fails at HEAD (confirmed by stashing this bead's changes and running against commit 62a4ddeb5, the sase-j9.1 commit) — the new default `-`/minus binding for `collapse_panel_folds` conflicts with the test's `stitches_next: minus` override, so the override silently reverts to default `j` instead of applying. Pre-existing regression from sase-j9.1, not caused by sase-j9.2.

[2026-08-11T00:02:17Z · sase-j9.2] Verified: just install; just check (all gates green except a pre-existing unrelated symvision whitelist staleness for closed bead sase-j3, confirmed via direct symvision run and git-stash diff against HEAD); just test-scoped (7410 passed, only the pre-existing unrelated sase-j9.1 keymap-conflict test fails, confirmed failing at HEAD too); just test-visual (651 passed, 1 skipped, after fixing/regenerating 4 footer-chip PNG goldens and rewriting a 5th test that exercised the retired whole-panel H ladder, which the prior session's sweep had missed). Hint-intent collapse mode, ladder retirement, footer/help/keymap label resync, and docs are all in place per the phase-hint plan section.

## Dependencies

- **Depends on:** [sase-j9.1](sase-j9.1.md) ✓ · ⧖ 2026-08-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-j9.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-j9.2/README.md) | [sase-j9.2](sase-j9.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9608b16`](https://github.com/sase-org/sase/commit/9608b163e98c3b207a7679eb57fe4c7106a580f7) | feat(ace): give H a hinted fold collapse on a selected tribe panel | [sase-j9.2](sase-j9.2.md) | 2026-08-10 20:03:16 EDT |
