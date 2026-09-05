# Bead: sase-wm.4 — Hint line, key help, docs, and PNG snapshot goldens

[Bead Pages](../README.md) / [sase-wm](README.md) / sase-wm.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.e](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.e.md) · **Assignee:** `sase-wm.4` · **Size:** medium
**Created:** 2026-09-04 11:59:02 EDT · **Closed:** 2026-09-04 23:24:21 EDT
**Plan:** [202609/projects\_tab\_init.md](https://github.com/sase-org/sase--plans/blob/main/202609/projects_tab_init.md)

## Description

polish: surface the new keys in the Projects hint line and key help, document the flow in `docs/ace.md`, `docs/configuration.md`, and `docs/init.md`, and pin the modal's visual states — single-project update, mixed all-projects, danger variant, TTY-blocked, diff expansion, and narrow terminal — with PNG snapshot goldens.

## Notes

[2026-09-05T03:23:41Z · sase-wm.4] Hint line: added `i init  I init all` after the sub-tab segment and dropped `F force after block` to make room on the overflowing 120-col line. Force remains in key help and docs.

[2026-09-05T03:24:21Z · sase-wm.4] Verified: Projects hint line shows i init / I init all (dropped F force after block); help lists i/I under Admin Center Projects; docs/ace.md, docs/configuration.md, and docs/init.md cover the init flow; six InitPlanModal PNG goldens (single, mixed --all, danger, TTY valve, diffs, narrow) plus refreshed Projects and help goldens pass just test-visual; just check passed; no leftover --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-wm.3](sase-wm.3.md) ✓ · ⧖ 2026-09-04
- **Blocks:** [sase-wm.5](sase-wm.5.md) ◐ · ⧖ 2026-09-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wm.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wm.4/README.md) | [sase-wm.4](sase-wm.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`69b5463`](https://github.com/sase-org/sase/commit/69b5463c35c750711c74baf7832a16a69dc11ee8) | feat(ace): document Projects init keys and pin InitPlanModal goldens | [sase-wm.4](sase-wm.4.md) | 2026-09-04 23:26:06 EDT |
