# Bead: sase-19x.11.3 — Verify and improve card-block navigation latency

[Bead Pages](../README.md) / [sase-19x.11](sase-19x.11.md) / sase-19x.11.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19x.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.land.md) · **Assignee:** `sase-19x.11.3` · **Size:** medium
**Created:** 2026-09-26 14:48:01 EDT · **Closed:** 2026-09-26 16:44:04 EDT
**Plan:** [202609/card\_block\_landing\_gaps.md](https://github.com/sase-org/sase--plans/blob/main/202609/card_block_landing_gaps.md)

## Description

block-performance: profile block cycling and sticky-Reply j/k, remove avoidable work, and record controlled latency against the original target and baseline.

## Notes

[2026-09-26T20:43:24Z · sase-19x.11.3] PROPOSED FOLLOW-UP: just _lint-symvision red on clean base too — private-misuse _legacy_sase_shell_syntax_enabled (agent/legacy) and _sync_scrollbar_position (main_view_blocks, from sibling 11.1); needs owner cleanup, blocks just check green

[2026-09-26T20:43:35Z · sase-19x.11.3] PROPOSED FOLLOW-UP: 3 decks-dir test failures reproduce identically on clean base (test_files_probe_empty_kinds, test_preferred_card_and_partial_empty_body via AgentType.PROC_SHELL turn-rename fallout, test_files_ctrl_j_scrolls_page_anchor_to_top flake); needs land-agent triage with 11.1 note 4 full-suite list

[2026-09-26T20:43:45Z · sase-19x.11.3] PROPOSED FOLLOW-UP: block-cycle bench arm captures n=16..20 of 20 keys across runs (paints coalesce at 0.01s spacing now that cycles are faster); consider wider key spacing or per-key paint gating for stable sample counts

[2026-09-26T20:44:04Z · sase-19x.11.3] Block-cycle: removed redundant full show_main_document re-show on block-only swaps (state-only preferred-card record); in-process 50ms to 4.5ms per cycle. Bench A/B same host: sticky SINGLE next p50 19.0 to 13-16ms, p95 50 to 21-48ms (at/better than prior flag-off 15.0/20.8, no feature regression); LEFT_RIGHT next p50 37.6 to 25-27ms; cycle median 52 to 32-43ms (under 50ms bar, prefer-improvement met). SINGLE prev p95 14.9 meets 16ms when host permits; remaining tails are host scheduler stalls (single samples to 272ms). Regression tests: focused cycle/select stick without document re-show (cursor, follow, rail, split independence). Base-red symvision (2 private-misuse) and 3 decks test failures reproduce on clean base, recorded as follow-ups.

## Dependencies

- **Depends on:** [sase-19x.11.1](sase-19x.11.1.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19x.11.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19x.11.3/README.md) | [sase-19x.11.3](sase-19x.11.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`64fae01`](https://github.com/sase-org/sase/commit/64fae010f3674b17b485e9a7c4c2407b9214d8d5) | perf(ace-tui): cut block-cycle and sticky-Reply navigation latency (sase-19x.11.3) | [sase-19x.11.3](sase-19x.11.3.md) | 2026-09-26 16:45:35 EDT |
