# Bead: sase-wm.2 — The i/I gestures, the InitPlanModal preview, and the streaming apply proc

[Bead Pages](../README.md) / [sase-wm](README.md) / sase-wm.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.e](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.e.md) · **Assignee:** `sase-wm.2` · **Size:** large
**Created:** 2026-09-04 11:58:58 EDT · **Closed:** 2026-09-04 19:56:14 EDT
**Plan:** [202609/projects\_tab\_init.md](https://github.com/sase-org/sase--plans/blob/main/202609/projects_tab_init.md)

## Description

flow: wire `i`/`I` through the full Projects keymap chain, plan off-thread via a session-worker `sase init … --check --json` proc, show the `InitPlanModal` preview with per-planner rows, warnings, blockers, and full diffs, and on confirm submit exactly one streaming `sase init … --yes` session proc with a dedup key and an exclusive scope, then toast and refresh in place.

## Notes

[2026-09-04T23:56:14Z · sase-wm.2] Implemented i/I init flow: keymap chain, InitScope/payload/diffs, InitPlanModal, session-worker check+apply with sase-init exclusive scope, in-place reload. just install, just check lint (ruff/mypy/symvision/toobig) passed; targeted init-flow tests passed; Projects PNG goldens stayed green. just check escalated (schema+default_config) and the full lane failed two origin/master-preexisting tests (contract_manifest 63 vs 62 budget; agent list nested monitor 2m/3m vs 2m/2m). just test-visual had 14 unrelated snapshot mismatches, none on config_center_projects.

## Dependencies

- **Depends on:** [sase-wm.1](sase-wm.1.md) ✓ · ⧖ 2026-09-04
- **Blocks:** [sase-wm.3](sase-wm.3.md) ✓ · ⧖ 2026-09-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wm.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-wm.2.md) | [sase-wm.2](sase-wm.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`29ce9cd`](https://github.com/sase-org/sase/commit/29ce9cd8b202e6bfe6c1716ad773c25542b31ddc) | feat(ace): add Projects tab i/I init plan modal and streaming apply | [sase-wm.2](sase-wm.2.md) | 2026-09-04 22:10:36 EDT |
