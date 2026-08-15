# Bead: sase-mc.5 — Complete provider-disable Models-panel correctness and acceptance

[Bead Pages](../README.md) / [sase-mc](README.md) / sase-mc.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-mc.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-mc.land.md) · **Assignee:** `sase-mc.5.land`
**Created:** 2026-08-15 16:11:45 EDT · **Closed:** 2026-08-15 18:50:23 EDT
**Plan:** [202608/provider\_disable\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/provider_disable_completion.md)

## Description

Provider disabling remains off the Textual event loop, rejects disabled custom targets, reports only real routing changes, and satisfies the original behavior and visual acceptance matrix.

## Notes

[2026-08-15T22:50:23Z · sase-mc.5.land] Preserved a user-moved Models-panel highlight when a provider snapshot finishes without an explicit keep; first-paint still lands on launch:default_model; explicit keep still wins; missing rows still fall back to the first launch row. Delayed-snapshot regression plus explicit-keep and missing-row tests added. Focused Models/provider suite passed (56). Diff-scoped just check lane: 723 passed; lint/format/mypy/validation passed. Unrelated stale-symvision epic-symbol failure on sase-m9.3.1.2 recorded on sase-m9.3.1.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mc.5.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-mc.5.land.md) | [sase-mc.5](sase-mc.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5511f04`](https://github.com/sase-org/sase/commit/5511f04ed37e0545984957e17e52247cc3fa3256) | fix(tui): keep Models selection across provider snapshots | [sase-mc.5](sase-mc.5.md) | 2026-08-15 18:51:27 EDT |
