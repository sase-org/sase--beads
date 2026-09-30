# Bead: sase-1d7.7 — Precise bulk-ack scope and a time-bound explicit undo

[Bead Pages](../README.md) / [sase-1d7](README.md) / sase-1d7.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0uc](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0uc.md) · **Assignee:** `sase-1d7.7` · **Size:** small
**Created:** 2026-09-30 07:18:15 EDT · **Closed:** 2026-09-30 12:38:18 EDT
**Plan:** [202609/unread\_ack\_reliability\_and\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202609/unread_ack_reliability_and_tui_responsiveness.md)

## Description

bulk-ack-scope-and-undo: make the bulk-ack target set share one predicate with the header unread count across tabs, collapsed clans and tribes, and replace the silent toggle with a toast-announced 10 second undo window.

## Notes

[2026-09-30T16:37:46Z · sase-1d7.7] PROPOSED FOLLOW-UP: tools/validate_sase_core_rs prompt-prediction probe fails on clean base (confident=False, ghost=[] vs expected confident=True, ghost=[the]); blocks every just recipe via _setup line 141

[2026-09-30T16:37:58Z · sase-1d7.7] PROPOSED FOLLOW-UP: visual tab-strip goldens empty/query_hides/feed_unavailable time out in wait_for_svg_contains on clean base (shared-host slowness); attention golden with off-tab unread passes with the all-tabs header count

[2026-09-30T16:38:18Z · sase-1d7.7] bulk-ack uses shared predicate over query_result+with_children+agents (toast==header incl collapsed/off-tab); 10s undo window with configured-chord toast; verified: 6 new + 144 neighboring tests pass, ruff fmt/lint + full mypy clean for touched files, attention visual golden passes; just-check _setup blocked by pre-existing core-validator probe failure reproduced on clean base (recorded as follow-up)

## Dependencies

- **Depends on:** [sase-1d7.6](sase-1d7.6.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d7.8](sase-1d7.8.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d7.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d7.7/README.md) | [sase-1d7.7](sase-1d7.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`af0ac9d`](https://github.com/sase-org/sase/commit/af0ac9d6acf9852276c6af6ccae220cb61ec10c6) | feat(agents): precise bulk-ack scope and time-bound explicit undo (sase-1d7.7) | [sase-1d7.7](sase-1d7.7.md) | 2026-09-30 12:40:22 EDT |
