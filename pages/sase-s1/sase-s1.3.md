# Bead: sase-s1.3 — Eliminate stale cursor paint from visual snapshots

[Bead Pages](../README.md) / [sase-s1](README.md) / sase-s1.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0al](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0al.md) · **Assignee:** `sase-s1.3` · **Size:** medium
**Created:** 2026-08-22 12:30:20 UTC
**Plan:** [202608/restore\_github\_actions.md](https://github.com/sase-org/sase--plans/blob/main/202608/restore_github_actions.md)

## Description

visual-cursor-convergence: normalize focused and blurred input cursor caches before accepting a converged visual frame.

## Notes

[2026-08-22T13:18:34Z · sase-s1.3] PROPOSED FOLLOW-UP: Artifacts-tab 120x40 goldens omit the split badge — confirm_dialog_neutral and sibling artifacts snapshots fail locally with ~6605 pixels at PNG y=91-115 where actual paints the teal {█} split badge and expected is empty; reproduced on HEAD with the old focused-only cursor helper, independent of sase-s1.3 caret-cache repair. Do not mass-rebase; triage whether goldens predate badge accent paint.

## Dependencies

- **Blocks:** [sase-s1.6](sase-s1.6.md) ◐ · ⧖ 2026-08-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s1.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-s1.3.md) | [sase-s1.3](sase-s1.3.md) | 0 |
