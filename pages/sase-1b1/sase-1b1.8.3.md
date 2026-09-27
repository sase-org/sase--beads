# Bead: sase-1b1.8.3 — Live wide/narrow drive of deck views and the acceptance checklist

[Bead Pages](../README.md) / [sase-1b1.8](sase-1b1.8.md) / sase-1b1.8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1b1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1b1.land.md) · **Assignee:** `sase-1b1.8.3` · **Size:** small
**Created:** 2026-09-27 14:53:06 EDT · **Closed:** 2026-09-27 17:09:49 EDT
**Plan:** [202609/deck\_views\_landing\_remainder.md](https://github.com/sase-org/sase--plans/blob/main/202609/deck_views_landing_remainder.md)

## Description

live-verify: drive the real TUI with sase screenshot at wide and narrow widths (P, Ctrl+J, split, zoom). Confirm the D5 title-legibility test and walk the parent plan's acceptance checklist. Fix small gaps and regenerate and inspect any golden that changes.

## Notes

[2026-09-27T20:53:44Z · sase-1b1.8.3] Live wide/narrow drive done 2026-09-27 (sase screenshot, real sase tui, no code changes). Wide 180x40: P cycled MAIN fixed page-blocks -> spread -> page-cards (badge always truthful); Ctrl+J moved Context 1/2 -> Reply 2/2 with badge stable (vacuous-request rule holds live); | split MAIN+FILES with compact rungs; Z zoomed FILES empty (no badge, correct for empty deck); Ctrl+F focus switch + P persisted. Narrow 120x40 split: tiny rung MAIN C.A 1/2 legible. Narrow 100x40: generic stacked layout squeezes deck to slivers (responsive behavior, not deck-owned). D5 confirmed at every width: title alone tells deck, spread-vs-paged, inline-vs-paged, auto-vs-fixed, plus rail cue (page N/M, main/files/tools/final counts). Restart: P-set fixed spread saved to ace_agents_deck_state.json, survived graceful q quit, and a fresh TUI restored spread-fixed badge. Acceptance: P always produced a change (no no-ops); badge never mislabeled; empty-deck P correctly hidden; views/cards/focus persist across quit/restart.

[2026-09-27T20:54:30Z · sase-1b1.8.3] PROPOSED FOLLOW-UP: six agents_deck_view PNG goldens fail on clean tree (0.2-1.2% pixels) from two unrelated drifts, need owner triage + regen: (1) footer hint [/] blocks -> (/) blocks from sase-1bc.1 bracket-to-paren move; (2) AGENT block-header selected-row background from sase-1b1.8.2 badge-first deferred apply. Inspected actual vs expected crops; deck badges/rails/bodies identical. Do not bless in this phase.

[2026-09-27T20:54:41Z · sase-1b1.8.3] PROPOSED FOLLOW-UP: concurrent/abrupt-death deck-state save race: killing screenshot TUI windows with tmux kill-window coincided with ace_agents_deck_state.json reverting to auto/single (single-window P-save, graceful-q preserve, and fresh-launch restore all verified working). If a dying or second concurrent TUI saves transitional/empty state last-writer-wins, it clobbers fixed views. Consider guarding saves against tearing down or concurrent writers.

[2026-09-27T21:09:25Z · sase-1b1.8.3] PROPOSED FOLLOW-UP: just check / sase tool run check red on clean tree at lint (symvision): usage_windows.py:141,467,487,517 pragmas reference sase-telegram symbols (usage_windows_report, resolve_usage_provider, request_usage_windows_refresh, live_usage_refresh_operations) missing from the linked sase-telegram checkout. Unrelated to deck views; needs the owning epic to update pragmas or the telegram checkout.

[2026-09-27T21:09:49Z · sase-1b1.8.3] Live wide/narrow drive verified: P cycle, Ctrl+J stable badge, split/zoom, D5 legible at 180/120/100 cols, views persist across graceful quit/restart (bug-for-bug notes recorded). No code changes. epic-symbols clean. just check: all lints pass except pre-existing symvision red (sase-telegram pragmas, recorded as follow-up); 6 deck goldens fail on clean tree from sase-1bc footer drift + 8.2 settle pixels (recorded as follow-up, badges identical).

## Dependencies

- **Depends on:** [sase-1b1.8.1](sase-1b1.8.1.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1b1.8.2](sase-1b1.8.2.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b1.8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b1.8.3/README.md) | [sase-1b1.8.3](sase-1b1.8.3.md) | 0 |
