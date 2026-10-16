# Bead: sase-1lc.8 — Finish the clan waves landing

[Bead Pages](../README.md) / [sase-1lc](README.md) / sase-1lc.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1lc.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lc.land.md) · **Assignee:** `sase-1lc.8.land`
**Created:** 2026-10-15 23:30:16 EDT · **Closed:** 2026-10-16 03:13:25 EDT
**Plan:** [202610/clan\_waves\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202610/clan_waves_landing_repairs.md)

## Description

The clan wave feature matches its approved design end to end. sase-core owns the whole wave layout through the planned wire, and the Python adapter only consumes it. Wave states, the gutter, the WAVES ladder, and the JUMP legend behave as specified. The TUI import budget passes again, and the clan-wave glossary term renders correctly.

## Notes

[2026-10-16T06:37:13Z · sase-1lc.8.land] LANDING FOLLOW-UP TRIAGE (sase-1lc.8.land; completed before remaining-work tale): reviewed every note on sase-1lc.8.1/.2/.3 and applied /sase_new_task (same-type/all-type semantic searches, last-week task sweeps, active-epic sweep).
- .8.1 #1 + .8.2 #1 + .8.3 #1 (generated-doc formatting): one duplicate proposal, causally owned by active docs epic sase-1le / phase .8; independent check ToolRun 129a12ae52c8dfb624dc0c3fa1f3fe33 fails there on clean d5efed6535. Corroborating DISCOVERED ISSUE appended to sase-1le; no task.
- .8.2 #2 + .8.3 #2 (render_cli mypy): one duplicate proposal; reproduced all 8 errors, source introduced by docs phase sase-1le.16 commit 8f22863f32. Routed with detailed evidence to active sase-1le, no task.
- .8.3 #3 (private _rows_by_suffix import): NOT an unrelated follow-up. just symvision independently exits 1 on exactly this epic-introduced cross-file private import. Keep as epic work in the remaining-work tale; no task.
- .8.3 #4 terminology: reproduced the three failing nodes, all findings in generated docs/reference/glossary.md, design-decisions.md, cli/gate.md. Routed to active docs epic sase-1le (.8/.16); no task. Existing sase-1hr is a different root cause (source-string allowlist after a test split); its currently passing node is not corroborated/reopened.
- .8.3 #4 PDF/social-card: reproduced both named failures already witnessed and recorded on sase-1le; included corroboration there, no task.
No proposal declined except duplicate task creation for the reasons above. No new unrelated task was needed. Preserve these outcomes in the final close note.

[2026-10-16T06:37:57Z · sase-1lc.8.land] LANDING VERIFICATION at d5efed6535: read the epic scope, all notes on .8.1/.2/.3, approved repair plan and parent Design, primary commits 04fee05559/375bceb6ea/d5efed6535 and linked-core 4c83f2de (pinned). Source confirms key-based wire with serde defaults and allow_threads, ordered placements/ghost separation/duplicate-name handling and required core shape/equality tests; adapter consumes core layout; anchor-only state fold; Done+ghost done; prefer-non-child workflow lanes; COLLAPSED ladder rows; shared after phrase; singular/zero wording; mixed fleet repaint; authorized Clan Wave strand repair; clan-only divider field; same-row separator rendering; title budget and deferred imports. 186 focused tests PASS, including actual Rust-backed adapter, states, gutters, ladder, roster, jump, mixed fleet diff and import budget. Import closure is 3519, +0 vs 91350ad5b6^; cap was not raised. No unrelated commits landed after this repair epic started / first commit: HEAD..origin/master empty, three repair commits only; linked core likewise only its repair commit. Approved memory decision honored (only clan-wave strand changed; generated indexes/shims regenerated). No --epic-symbol entries for sase-1lc.8 or sase-1lc.
NOT CLOSABLE YET: (1) just symvision fails exactly on private _rows_by_suffix imported into _clan_wave_gutter; this was introduced by .8.2 and .8.3 #3 must remain epic work. (2) _collapsed_selection_for_columns still adds _selection_divider_count to target-slot capacity after divider rendering moved into separators. Repro via test_agent_jump_legend helpers: labels a0,a1,b0,b1, legend groups wave 1,wave 1,wave 2,wave 2. At widths 16/18/20/24 actual renderer shows a0,a1,+2, yet all four fit two columns (two 15-cell rows) with no divider across the row break; _collapsed_grid_fits(all_four, gaps, 2,16) is True. Select/fitting must use real row widths and overflow, not whole-slot reservations for unrendered row-break dividers. Plan a single medium tale for these two bounded repairs plus this epic and parent closeout. Whole check is still blocked by independently reproduced docs failures, all follow-ups triaged in the prior note and on active docs epic sase-1le; no check-full was run.

[2026-10-16T07:13:25Z · sase-1lc.8.land--2] CLOSEOUT (final closeout tale): source/commit/decision review at d5efed6535 plus uncommitted tale repairs; key-based Rust wire with serde defaults and allow_threads, ordered placements/ghost separation/duplicate-name handling and core shape/equality tests; adapter consumes core layout; anchor-only state fold; Done+ghost done; prefer-non-child workflow lanes; COLLAPSED ladder rows; shared after phrase; singular/zero wording; mixed fleet repaint; authorized Clan Wave strand repair; clan-only divider field; same-row separator rendering; title budget and deferred imports. No drift: HEAD d5efed6535, HEAD..origin/master empty, linked-core 4c83f2de pinned, three repair commits only, no unrelated commits. Memory decision glossary_clan_wave_strand=yes already implemented; no memory edit. REPAIR 1: renamed _rows_by_suffix to rows_by_suffix in models/_agent_tree_clan.py, updated in-file callers and widgets/_clan_wave_gutter.py import/call; keeps prefer-non-child behavior, location, lazy loading; just symvision now passes. REPAIR 2: grouped JUMP fitting uses actual rendered space in widgets/_agent_jump_legend.py; deleted _selection_divider_count; dividers render as 3-cell separator only between same-row neighbors, never at row edge/break/overflow; selection reserves only real overflow cell via _collapsed_shown_count; grid fitter accounts actual separator+overflow widths; two-row/width/unique/in-flight-first/always-shown and accurate +N M overflow preserved; no-group path unchanged. Tests updated only where they pinned old slot reservation (grouped_shown equality, bounded-search expectation) plus new row-break and overflow regression tests. VERIFICATION: 119 focused tests pass (jump_legend/gutter/clan_waves models); import closure 3519 +0 vs 91350ad5b6^; just fix clean; just symvision passes; fix-tui-screenshots update applied complete (1 updated agents_jump_panel_layered_wave_dividers_120x40, 11 unchanged, 0 skipped, pruning_skipped_reason null, no pruning skip); inspected all 5 changed goldens (3 ladder + 60/120 jump): no row-edge dividers, padded divider columns via separator gaps, accurate overflow (+3 in 120-col with 0/1/2 shown, interior dividers in 60/80-col), targets shown whenever two-row fits (120-col shows max 3 in narrow split; grouped 4-fit at 16/18/20/24 with boundary at break). Two strict --check captures over clan/clan-panel/tribe/JUMP (8 files, 29 nodes each): default TZ clean (48 unchanged); TZ=UTC shows 2 pre-existing TZ-sensitive drifts in agents_clan_tree_collapsed/expanded_120x40 (359/412 px, unrelated clan-tree snapshots, not updated). FOLLOW-UPS PRESERVED from prior triage (no new tasks, no docs changes): .8.1#1+.8.2#1+.8.3#1 generated-doc Prettier drift owned by sase-1le/.8; .8.2#2+.8.3#2 render_cli mypy 8 errors from sase-1le.16 commit 8f22863f32; .8.3#4 terminology 3 nodes + pdf/social-card KNOWN on sase-1le; .8.3#3 retained as epic work and fixed here. Whole check still blocked by known docs failure: ToolRun 669e8e238f210fbd4db7abee938d8447 fails at fmt-docs-check on docs/reference/design-decisions.md (known render_glossary/render_design_decisions drift, independently reproduced by ToolRun 129a12ae52c8dfb624dc0c3fa1f3fe33 on clean d5efed6535). No check-full run.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1lc.8.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lc.8.land.md) | [sase-1lc.8](sase-1lc.8.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b971b55`](https://github.com/sase-org/sase/commit/b971b55fd6f5d662069deeb32968decee514f094) | feat(ace): fit grouped JUMP targets to rendered space and publish suffix index | [sase-1lc.8](sase-1lc.8.md) | 2026-10-16 03:17:29 EDT |
| sase--plans | [`sase--plans@f91273e`](https://github.com/sase-org/sase--plans/commit/f91273eed6a13154909c62b538b951f8c0dbabc8) | docs(plans): mark clan-wave landing plans done | [sase-1lc.8](sase-1lc.8.md) | 2026-10-16 03:21:53 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1lc.8.3][1] | need epic phase status and remaining work | 1 |
| read-by | [agent:sase-1lc.8.land--2][2] | closeout reread for final verification | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1lc.8.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1lc.8.land.md

<!-- sase:referenced-by:end -->
