# Bead: sase-1lc.8.3 — JUMP legend dividers, legend performance, and the TUI import budget

[Bead Pages](../README.md) / [sase-1lc.8](sase-1lc.8.md) / sase-1lc.8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1lc.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lc.land.md) · **Assignee:** `sase-1lc.8.3` · **Size:** medium
**Created:** 2026-10-15 23:30:17 EDT · **Closed:** 2026-10-16 02:19:21 EDT
**Plan:** [202610/clan\_waves\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/clan_waves_landing_repairs.md)

## Description

legend: scope dividers to layered clan rosters and draw them only between same-row neighbors, restore pre-epic legend layout cost, fix the title suffix budget, and take the five clan-wave modules off the TUI startup import path. Then regenerate and inspect the jump-panel goldens.

## Notes

[2026-10-16T06:18:28Z · sase-1lc.8.3] PROPOSED FOLLOW-UP: just fmt-docs-check render_glossary/render_design_decisions vs prettier drift fails identically on clean base tree, tracked on docs epic sase-1le

[2026-10-16T06:18:32Z · sase-1lc.8.3] PROPOSED FOLLOW-UP: just lint _lint-mypy fails in untouched tools/render_cli (list invariance, 8 errors) — pre-existing, same as sase-1lc.8.2 follow-up

[2026-10-16T06:18:37Z · sase-1lc.8.3] PROPOSED FOLLOW-UP: symvision flags private import _rows_by_suffix from _agent_tree_clan into _clan_wave_gutter (added by sase-1lc.8.2, untouched by this phase) — needs public rename or pragma per symvision memory

[2026-10-16T06:18:42Z · sase-1lc.8.3] PROPOSED FOLLOW-UP: terminology tests test_macro_terminology/test_sase_turn_terminology/test_agent_session_terminology fail identically on clean base tree (verified via stash); test_pdf_check_recipe and test_docs_social_card already KNOWN-witnessed to sase-1le

[2026-10-16T06:18:53Z · sase-1lc.8.3] Legend layout timings (collapsed, no groups, median of 7 fresh renderables): BEFORE 30t@80/120/200=4.97/7.12/9.89ms 100t@80/120/200=34.33/45.08/57.67ms; AFTER 30t=1.27/2.04/3.74ms 100t=2.65/3.53/6.06ms vs pre-epic 2.4/3.5/6.9ms — within noise. Import closure back to 3519 (+0 vs 91350ad5b6^).

[2026-10-16T06:19:21Z · sase-1lc.8.3] legend done: dividers scoped to layered clans via MemberRosterEntry.legend_group with separator-folded rendering (no row-edge dividers, divider-aware fitting); no-group layout restored to pre-epic closed form + width//8 cap (sweep-proven over 8 counts x 7 widths, single _collapsed_selection per candidate); title budget ignores bottom subtitle; 5 clan-wave modules off startup path (closure +0 at 3519). Verified: 112 focused tests pass, 9 goldens regenerated and pixel-inspected (legend-localized diffs), targeted --check clean twice (one TZ=UTC), clan j/k bench p95<16ms, import budget test passes, mypy clean on touched files; sase tool run check shows only base-identical failures (fmt-docs drift, render_cli mypy, symvision _rows_by_suffix, 3 terminology tests verified via stash, plus KNOWN pdf/social-card), all recorded as follow-ups

## Dependencies

- **Depends on:** [sase-1lc.8.2](sase-1lc.8.2.md) ✓ · ⧖ 2026-10-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lc.8.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lc.8.3/README.md) | [sase-1lc.8.3](sase-1lc.8.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d5efed6`](https://github.com/sase-org/sase/commit/d5efed653553978194eeb8f28192b7fe651da849) | feat(ace): scope layered wave dividers to clan roster and restore jump layout cost | [sase-1lc.8.3](sase-1lc.8.3.md) | 2026-10-16 02:21:23 EDT |
