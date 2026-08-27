# Bead: sase-uv.8 — Honour the AgentsViewport contract instead of discarding it

[Bead Pages](../README.md) / [sase-uv](README.md) / sase-uv.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ex](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ex.md) · **Assignee:** `sase-uv.8` · **Size:** large
**Created:** 2026-08-27 12:26:48 EDT · **Closed:** 2026-08-27 18:52:01 EDT
**Plan:** [202608/ace\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_tui_responsiveness.md)

## Description

viewport: wire the bounded read window through DirectAgentsDataProvider so a refresh stops building 430 agents to paint 12 rows; measurement-gated on whether the earlier phases already met budget.

## Notes

[2026-08-27T22:52:01Z · sase-uv.8] Auto-closed by `sase stitch create` after create_commit landed a805b0da2 ("feat(agents): add bounded viewport loading"). No verification is implied by this note. Reopen with `sase bead open sase-uv.8`, or pass `-B|--do-not-close-bead` on mid-flight commits.

## Dependencies

- **Depends on:** [sase-uv.4](sase-uv.4.md) ✓ · ⧖ 2026-08-27
- **Depends on:** [sase-uv.5](sase-uv.5.md) ✓ · ⧖ 2026-08-27
- **Depends on:** [sase-uv.7](sase-uv.7.md) ✓ · ⧖ 2026-08-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-uv.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-uv.8.md) | [sase-uv.8](sase-uv.8.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a805b0d`](https://github.com/sase-org/sase/commit/a805b0da2f23de59d628c9c16ff4855fb68d8a02) | feat(agents): add bounded viewport loading | [sase-uv.8](sase-uv.8.md) | 2026-08-27 18:49:33 EDT |
| sase-core | [`sase-core@07bd0f5`](https://github.com/sase-org/sase-core/commit/07bd0f589434f90c51faab4994c0ef0d4db1c31d) | feat(agent-scan): support windowed index reads | [sase-uv.8](sase-uv.8.md) | 2026-08-27 18:52:28 EDT |
