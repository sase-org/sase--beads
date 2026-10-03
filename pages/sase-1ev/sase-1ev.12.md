# Bead: sase-1ev.12 — Review watermark in the Changes lens

[Bead Pages](../README.md) / [sase-1ev](README.md) / sase-1ev.12

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vj.md) · **Assignee:** `sase-1ev.12` · **Size:** small
**Created:** 2026-10-02 14:43:21 EDT
**Plan:** [202610/memory\_history\_tui.md](https://github.com/sase-org/sase--plans/blob/main/202610/memory_history_tui.md)

## Description

watermark-tui: show the Changes lens header N-new chip and unreviewed row dots, add m to mark reviewed (optimistic, persisted off-thread), and add the quiet-time MEMORY sub-tab badge.

## Notes

[2026-10-03T08:26:01Z · sase-1ev.12] PROPOSED FOLLOW-UP: visual-lane convergence flake — hub-opening PNG tests intermittently time out in wait_for_visual_idle with pending_workers=[task] (a pre-existing thread worker, likely the history warmup sync); reproduces on the untouched flags suite in this environment, unrelated to watermark-tui

[2026-10-03T08:26:12Z · sase-1ev.12] PROPOSED FOLLOW-UP: just check red on pre-existing symvision staleness — Justfile _lint-symvision passes --epic-symbol sase-1eu(Geometry|GridSpec|geometry|main_pane) but bead sase-1eu is closed; Justfile untouched by watermark-tui, fails identically on clean tree

[2026-10-03T08:44:46Z · sase-1ev.12] PROPOSED FOLLOW-UP: just test-scoped shows 49 failed + 10 errors all pre-existing — 40 fail identically on clean tree (prompt-bar editor harness AttributeError, commit/pr-report meta, macro loader/highlight, pager three-panes, doctor, deck spread, startup sync, split keys), 9 pass on clean serial rerun (parallel-load flakes incl. 8 ERRORs); zero overlap with watermark-tui files

## Dependencies

- **Depends on:** [sase-1ev.11](sase-1ev.11.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ev.13](sase-1ev.13.md) ◐ · ⧖ 2026-10-02
- **Depends on:** [sase-1ev.9](sase-1ev.9.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ev.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.12/README.md) | [sase-1ev.12](sase-1ev.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0676975`](https://github.com/sase-org/sase/commit/0676975ef3624059393e9e058a43678f6c58e34f) | feat(memory-history-tui): Changes-lens review chip + unreviewed dots + m to mark reviewed, MEMORY badge (sase-1ev.12) | [sase-1ev.12](sase-1ev.12.md) | 2026-10-03 04:46:01 EDT |
