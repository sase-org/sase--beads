# Bead: sase-1dr.11 — Memory panel entry points and History row

[Bead Pages](../README.md) / [sase-1dr](README.md) / sase-1dr.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3o](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3o.md) · **Assignee:** `sase-1dr.11` · **Size:** medium
**Created:** 2026-09-30 19:09:37 EDT · **Closed:** 2026-10-01 10:54:04 EDT
**Plan:** [202609/memory\_history.md](https://github.com/sase-org/sase--plans/blob/main/202609/memory_history.md)

## Description

memory-panel: add the Memory panel `H` binding, which opens the selected note, web, or strand in the pager at now, and the `C` binding, which opens the changes feed. Add a History card row with a mini sparkline, loaded off-thread after paint. Wire the keymap everywhere the gotchas require, including default_config.yml, and add visual goldens.

## Notes

[2026-10-01T14:52:41Z · sase-1dr.11--2] PROPOSED FOLLOW-UP: symvision base failures HandoffSubmitResult (handoff_launch.py), StarterResolution (starter.py), owner_ref (owner.py) reproduce identically on clean base tree; just check symvision stage fails on master too

[2026-10-01T14:54:04Z · sase-1dr.11--2] H/C bindings wired in keymaps, default_config.yml, schema, docs; History card row loads off-thread with sparkline via history_value_text; unit tests 13 passed, keymaps 19 passed, visual PNG goldens 2 passed, ruff+mypy clean on touched files; symvision shows only the 3 base-tree failures (StarterResolution, HandoffSubmitResult, owner_ref) recorded as follow-up

## Dependencies

- **Depends on:** [sase-1dr.10](sase-1dr.10.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1dr.12](sase-1dr.12.md) ◐ · ⧖ 2026-09-30
- **Depends on:** [sase-1dr.7](sase-1dr.7.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1dr.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1dr.11.md) | [sase-1dr.11](sase-1dr.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`eb2e02d`](https://github.com/sase-org/sase/commit/eb2e02dbb87104c832360674133acb9234b60088) | feat(sase-1dr.11): memory panel history entry points and History row | [sase-1dr.11](sase-1dr.11.md) | 2026-10-01 10:56:28 EDT |
