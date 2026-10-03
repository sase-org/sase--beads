# Bead: sase-1ev.4 — Step through versions on the card

[Bead Pages](../README.md) / [sase-1ev](README.md) / sase-1ev.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0vj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0vj.md) · **Assignee:** `sase-1ev.4` · **Size:** medium
**Created:** 2026-10-02 14:43:08 EDT · **Closed:** 2026-10-02 21:46:38 EDT
**Plan:** [202610/memory\_history\_tui.md](https://github.com/sase-org/sase--plans/blob/main/202610/memory_history_tui.md)

## Description

card-stepping: add ( ) { } stepping on the card using the pager's moment model, with prefetched bodies and atomic pill/body swaps. Includes the past read view with past frontmatter, the violet past frame, H at the exact pin, mutation and link guards, unaudited strand pasts, arrival rules, the first Esc ladder rung, footer destination verbs, and the help Time group.

## Notes

[2026-10-03T01:45:46Z · sase-1ev.4] PROPOSED FOLLOW-UP: lint (feature flags) fails on rule 7 — closed flag bead sase-1ey still has a surviving three_pane_splits definition; reproduces identically on the clean base tree, unrelated to card-stepping

[2026-10-03T01:46:04Z · sase-1ev.4] PROPOSED FOLLOW-UP: refresh Memory-pane PNG goldens — the card footer now shows ( ) { } step verbs (time-strip goldens shift) and card-stepping needs new past-read/strand-past/tombstone goldens at 120x40, 80x24, dark+light via just fix-tui-screenshots with inspection

[2026-10-03T01:46:15Z · sase-1ev.4] PROPOSED FOLLOW-UP: record memory.history.step warm step p95 (budget <=30ms), j/k p95, and zero-stall rapid-stepping numbers; the memory.history.step trace span is in place

[2026-10-03T01:46:38Z · sase-1ev.4] card-stepping done: ( ) { } steps via pager moment model with prefetched bodies and atomic pill/body swaps; past read view with past frontmatter, violet past frame (deleted style for tombstones), H at exact pin, a/e/d/I/add-strand and link guards, unaudited strand pasts, per-subject arrival pins, Esc filter-then-pin-then-close rung (q closes direct), time_verbs_for_moment footer verbs with o edit now, help Time group, full 4.10 keymap plumbing, memory.history.step span. Verified: 16 new tests + 167 related tests green; ruff/format/mypy/symvision/keep-sorted/validate green. lint (feature flags) fails identically on clean base (sase-1ey/three_pane_splits, pre-existing, noted as follow-up); PNG golden refresh + step p95 measurement noted as follow-ups.

## Dependencies

- **Depends on:** [sase-1ev.3](sase-1ev.3.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1ev.5](sase-1ev.5.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ev.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ev.4/README.md) | [sase-1ev.4](sase-1ev.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b4b1e32`](https://github.com/sase-org/sase/commit/b4b1e327545ab801621e7dabe8ceb6472a5f3693) | feat(memory-pane): add card time-stepping with pinned past view | [sase-1ev.4](sase-1ev.4.md) | 2026-10-02 21:49:04 EDT |
