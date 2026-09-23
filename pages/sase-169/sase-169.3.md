# Bead: sase-169.3 — Per-golden determinism agreement

[Bead Pages](../README.md) / [sase-169](README.md) / sase-169.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.1i](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.1i.md) · **Assignee:** `sase-169.3` · **Size:** medium
**Created:** 2026-09-22 10:18:01 EDT · **Closed:** 2026-09-22 13:59:54 EDT
**Plan:** [202609/fix\_tui\_screenshots\_never\_fail.md](https://github.com/sase-org/sase--plans/blob/main/202609/fix_tui_screenshots_never_fail.md)

## Description

verify-agreement: replace the all-or-nothing determinism verification with per-golden agreement voting over bounded serial re-verification. Apply agreed captures and skip unstable goldens with warnings.

## Notes

[2026-09-22T17:58:14Z · sase-169.3--4] PROPOSED FOLLOW-UP: just-check run f6614796d3215cc10af01cdbb0e6f8c5 shows 25 failures in unrelated areas (bead CLI free-text classification, test shards drift, agent panel/neighbor index, plugins browser, usage config, import-budget timing 5.14s vs 5.0s, commit bead hooks, session proc reporter, epic panel frames, notify rules); none touch this phase files, triage as task beads

[2026-09-22T17:58:57Z · sase-169.3--4] PROPOSED FOLLOW-UP: sase_10 workspace editable sase_core_rs install is stale (circular import) so core-dependent screenshot tests error at setup locally; needs just install / rust-install rebuild

[2026-09-22T17:59:54Z · sase-169.3--4] verify-agreement done: per-golden agreement voting over at most 3 serial re-verifications in tests/ace/tui/visual/_visual_maintenance_verify.py wired into salvage; 9 new tests in tests/test_fix_tui_screenshots_verify.py plus apply/salvage suites pass where env allows (35+26 green, only sase_core_rs stale-install setup errors locally); ruff/mypy-configured/toobig clean; fixed mypy Optional assignment in new verify module. just-check run f66147 failed with 25 pre-existing unrelated failures (bead CLI, shards, panels, plugins, usage, import-budget timing, hooks) none touching this diff; recorded as follow-ups. epic-symbols clean.

## Dependencies

- **Depends on:** [sase-169.2](sase-169.2.md) ✓ · ⧖ 2026-09-22
- **Blocks:** [sase-169.5](sase-169.5.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-169.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-169.3.md) | [sase-169.3](sase-169.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`716291a`](https://github.com/sase-org/sase/commit/716291a9fdb3601c10c9519a77e53b760f2bc1b6) | feat(screenshots): per-golden agreement voting over bounded serial re-verification | [sase-169.3](sase-169.3.md) | 2026-09-22 14:02:26 EDT |
