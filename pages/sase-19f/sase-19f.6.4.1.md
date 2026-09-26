# Bead: sase-19f.6.4.1 — Render loaded multipliers on the remaining TUI surfaces

[Bead Pages](../README.md) / [sase-19f.6.4](sase-19f.6.4.md) / sase-19f.6.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-19f.6.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-19f.6.land.md) · **Assignee:** `sase-19f.6.4.1` · **Size:** medium
**Created:** 2026-09-26 08:08:38 EDT · **Closed:** 2026-09-26 08:46:59 EDT
**Plan:** [202609/queue\_multiplier\_loaded\_display.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_multiplier_loaded_display.md)

## Description

loaded-display: Treat a valid multiplier with no integer as authored capacity on the badge, header, wait lane, queue ladder, and clan and roster digests, and drop the two reintroduced sase-19f epic-symbol lines.

## Notes

[2026-09-26T12:30:12Z · sase-19f.6.4.1] PROPOSED FOLLOW-UP: just check symvision reports stale sase-19x.4 epic-symbols (phase_card_block, block_meta_for_session_shell, session_reply_heading) — bead sase-19x.4 is CLOSED; left untouched per design

[2026-09-26T12:46:20Z · sase-19f.6.4.1--1] PROPOSED FOLLOW-UP: just check fails only on pre-existing stale sase-19x.4 epic-symbols left untouched per design — exact symvision: Error: --epic-symbol sase-19x.4(phase_card_block): bead sase-19x.4 is closed; Error: --epic-symbol sase-19x.4(block_meta_for_session_shell): bead sase-19x.4 is closed; Error: --epic-symbol sase-19x.4(session_reply_heading): bead sase-19x.4 is closed. Base HEAD Justfile contains identical 3 lines; all other just check stages passed.

[2026-09-26T12:46:59Z · sase-19f.6.4.1--1] Loaded-multiplier display done: badge/header/wait-lane/queue-ladder/clan+roster digests treat valid multiplier with no integer as authored capacity; dropped two reintroduced sase-19f epic-symbol lines. Verified: test_queue_capacity_multiplier_display 17 passed; symvision without stale sase-19x.4 entries passes; just check all stages pass except 3 pre-existing stale sase-19x.4 symbols (closed bead, untouched per design, recorded as follow-up); epic-symbols for this phase: none.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-19f.6.4.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-19f.6.4.1.md) | [sase-19f.6.4.1](sase-19f.6.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d365706`](https://github.com/sase-org/sase/commit/d36570629759384df88a0c3ef4c818cdfd7b8d88) | feat(ace-tui): render loaded queue multipliers as authored capacity (sase-19f.6.4.1) | [sase-19f.6.4.1](sase-19f.6.4.1.md) | 2026-09-26 08:49:06 EDT |
