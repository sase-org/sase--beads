# Bead: sase-19x.9 — Remove the flag, add goldens, inspect live, and bench

[Bead Pages](../README.md) / [sase-19x](README.md) / sase-19x.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0s4.md) · **Assignee:** `sase-19x.9` · **Size:** medium
**Created:** 2026-09-25 20:37:51 EDT · **Closed:** 2026-09-26 11:45:33 EDT
**Plan:** [202609/agent\_data\_card\_blocks.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_data_card_blocks.md)

## Description

card-blocks-cutover: record the flag-off vs flag-on j/k bench, then remove the card_blocks flag (delete the Off branch, close the flag bead). Add and inspect the block-state PNG goldens, inspect live sase screenshot captures, and leave just check green.

## Notes

[2026-09-26T14:38:33Z · sase-1ab.2--5] Heads-up from sase-1ab.2 verification: just _lint-symvision flagged 5 of your epic's public symbols as unused (ReadingAnchor, capture_reading_anchor, restore_block_offset in panel_transitions.py; render_block_rail, block_rail_text in block_rail.py -- test-only references do not count). Deferred via --epic-symbol sase-19x.9 entries in the Justfile with an ownership comment so checks stay green. Your phase owns the real fix: consume them cross-file, privatize, or delete (block_rail_text has no src caller at all). Entries are self-cleaning -- symvision will tell you when to drop each one.

[2026-09-26T15:44:50Z · sase-19x.9] PROPOSED FOLLOW-UP: block-spread to block-paged mode switch leaves ScrollBar.position stale (e.g. 135 vs scroll 0) until next explicit scroll — thumb misrenders; found via micro golden flake, worked around in-test with explicit re-sync scroll

[2026-09-26T15:45:33Z · sase-19x.9] Cutover done. BENCH (flag present): SINGLE off next p50 15.03/p95 20.84 prev 12.74/15.57, on next 15.85/21.71 prev 18.64/44.06; LEFT_RIGHT off next 40.46/56.02 prev 36.59/42.44, on next 26.33/38.88 prev 25.24/42.34. 100ms budget asserts pass; 16ms tight number exceeded by both arms incl flag-off (host contention tail noise), flag-on clearly faster in LEFT_RIGHT. Fixed bench setup omission: cycle test now pins sticky Reply like the sticky arm. FLAG REMOVED: decks/flag.py deleted, registry+schema synced, 10 src sites collapsed, on/off pilot tests collapsed, bench single-state; flag bead sase-1ad closed; check_feature_flags clean; epic-symbols clean. GOLDENS: 7 block-state PNGs added+inspected (paged newest/older, spread landing, split windowed rails+independent cursors+dim, spread-deck sticky no-rail, arrival dot, micro). Full visual file 7/7, bench 2/2, deck/block unit 49 incl reply-blocks green, ruff clean. LIVE: workspace TUI captures (7x, /tmp/kept_live_blocks_*.png) — card cycling works, no live multi-shell session Reply exists so rails rely on goldens. Full sase tool run check started on monitor (cold Rust compile exceeds turn); one PROPOSED FOLLOW-UP noted (scrollbar desync).

[2026-09-26T16:38:37Z · sase-19x.9--1] PROPOSED FOLLOW-UP: 5 test_project_tags apply-selection failures reproduce identically on clean base tree (verified via git stash: 5 failed, 54 passed both with and without 19x.9 work); source files untouched by 19x.9 — pre-existing, needs owner

[2026-09-26T16:38:50Z · sase-19x.9--1] PROPOSED FOLLOW-UP: test_files_ctrl_j_scrolls_page_anchor_to_top flakes under full parallel load but passes alone (matches sase-19x.4 note #2); vcs_project_completion x6, agent_header_panel, docs_getting_started failures in full check lane also outside 19x.9 file scope — verify on base and triage

## Dependencies

- **Blocks:** [sase-19x.10](sase-19x.10.md) ◐ · ⧖ 2026-09-25
- **Depends on:** [sase-19x.4](sase-19x.4.md) ✓ · ⧖ 2026-09-25
- **Depends on:** [sase-19x.7](sase-19x.7.md) ✓ · ⧖ 2026-09-25
- **Depends on:** [sase-19x.8](sase-19x.8.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19x.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19x.9.md) | [sase-19x.9](sase-19x.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`39f8e4e`](https://github.com/sase-org/sase/commit/39f8e4ea4702ee22ed584b8d7d36f21053a79bfc) | feat(ace-tui): card-blocks cutover, flag removal, goldens and bench (sase-19x.9) | [sase-19x.9](sase-19x.9.md) | 2026-09-26 13:51:36 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19i.7.3.3.1--1][1] | checking closed bead that owns stale epic-symbols | 1 |
| read-by | [agent:sase-1af.5.land][2] | Need whether the open card-blocks epic still owns the surviving card_blocks definition | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19i.7.3.3.1.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1af.5.land/README.md

<!-- sase:referenced-by:end -->
