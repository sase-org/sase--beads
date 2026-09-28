# Bead: sase-1bn — Agents node rail and unmistakable deck zoom

[Bead Pages](../README.md) / sase-1bn

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.2h](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.2h.md) · **Assignee:** `sase-1bn.land`
**Created:** 2026-09-27 17:33:09 EDT · **Closed:** 2026-09-28 02:20:27 EDT
**Plan:** [202609/agents\_node\_rail\_and\_zoom.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_node_rail_and_zoom.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/agents_node_rail_and_zoom.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | [bead:sase-1bz][2] | The retry loop lives in sase-1bn.5's node-rail golden harness; the epic introduced the rail goldens |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/agents_node_rail_and_zoom.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1bz/README.md

<!-- sase:links:end -->

## Description

Ctrl+S turns the Agents-tab node sidebar into a fixed-width, row-for-row node rail that still shows every tribe, group, and node as glyphs. Z zoom hides the left column entirely and looks unmistakably different from the rail. Zoom never leaks into the saved Ctrl+S preference, and no key silently drops a split.

## Notes

[2026-09-28T00:21:02Z · sase-1b2.land] DISCOVERED ISSUE (sase-1b2.land, sase master 965248789b): symvision src/sase now fails only on 3 unused publics in src/sase/ace/tui/widgets/_agent_list_render_rail.py: rail_panel_title, rail_tooltip_text and rail_urgency (module from sase-1bn.2/.3, last touched 55e4bf73b2). The Justfile has no --epic-symbol entries for them. If in-progress sase-1bn.5/.7 will consume them, add epic-symbol entries keyed to those phases; otherwise privatize or delete them per the symvision memory.

[2026-09-28T02:52:45Z · sase-1bf.land] DISCOVERED ISSUE (sase-1bf.land, sase master 965248789b + this tale's 3 fixes, sase-core bc71eb2, tool run db269817c4f912574f05104c4e0a6782): landing sase-1bf required bumping sase-core-revision.txt (0e8981a -> bc71eb2, needed for managed-tmp wire 4), which made `just check`'s test-scoped selector distrust the closure and escalate internally to the full suite (per docs/lint_and_test.md; not a reason to run check-full). That full run surfaced a cluster of pre-existing failures that all trace to the in-progress agent-tab/rail work (sase-1bn.2-.7, not to sase-1bf):

- ImportError: `tests/ace/tui/test_agent_tab_cross_nav.py` and `test_agent_tab_scope_honesty.py` cannot import `scoped_agents_for_owner` from `sase.ace.tui.actions.agents._tab_scope` (not yet defined there). This same collection error also fails `tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection` (`pytest -m contract --collect-only` exits 2).
- `tests/test_axe_run_agent_exec_repeat_env.py` (6 tests): `_export_exec_agent_tab` in `src/sase/axe/run_agent_exec.py:213` reads `ctx.agent_meta`, but the tests' `MagicMock(spec=AgentExecContext)` fixture predates that attribute.
- `tests/ace/tui/test_agent_completion.py` (8 tests) and `tests/ace/tui/widgets/test_directive_completion_candidates.py` (2 tests): completion candidates now include an unexpected `("tab", ...)` entry the assertions don't account for.
- `tests/ace/tui/test_agent_list_watch_highlighted.py`, `tests/ace/tui/widgets/test_agent_header_panel.py`, `tests/ace/tui/test_copy_as_palette_entrypoints.py`, `tests/ace/tui/actions/test_prompts_overlay_entry_points.py`: assorted AgentList/header/palette assertion mismatches, plausibly the same rail/tab refactor (sase-1bn.7 covers palette/tooltip/help affordances).
- `tests/completion/test_kind_coverage.py`, `tests/completion/test_snapshot.py` (2 tests), `tests/completion/test_zsh_smoke.py`: CLI completion spec drift, plausibly downstream of the same directive/tab completion changes.
- `tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed`: static allowlist audit mismatch, plausibly a new agent-tab call site not yet reviewed into the allowlist.

None of these touch managed_tmp/launch-scratch/disk-footprint files, so sase-1bf's landing did not cause them and did not fix them; full evidence is on tool run db269817c4f912574f05104c4e0a6782 (`sase tool show db269817c4f912574f05104c4e0a6782 -F`). sase-1bn.7 is in_progress and may already be addressing part of this; if not, its land agent should triage and either fix or bead each root cause.

[2026-09-28T04:16:49Z · sase-1bn.land] LANDING TRIAGE (sase-1bn.land, master 52f7351ae). Follow-up outcomes: (a) sase-1bn.1 #1 stale test_final_panel_decoded_to_main_keeps_views: declined, test no longer exists on master. (b) sase-1bn.1 #2 symvision private _segment_section_identity: declined, already public (segment_section_identity) on master. (c) sase-1bn.3 #1 / sase-1bn.4 #1 / sase-1bn.6 #1 repo-wide symvision red, and epic note #1 rail_panel_title/rail_tooltip_text/rail_urgency: declined, direct symvision run on master is clean (rail_panel_title and rail_tooltip_text now consumed, rail_urgency privatized), and sase bead epic-symbols sase-1bn is empty. (d) sase-1bn.5 #1 first Ctrl+S swallowed after fold: not reproduced in 22 instrumented runs (6 serial by-project, 16 under -n 4), not shown to be epic-caused -> new flake task sase-1bz (linked related to sase-1bn). (e) sase-1bn.7 #1 glossary Node Panel strand: plan forbade memory edits in this epic -> memory task sase-1bx. (f) sase-1bn.7 #2 and epic note #2 failure clusters: only tests/ace/tui/test_agent_list_watch_highlighted.py::test_watch_highlighted_delegates_when_user_navigation is epic-caused (AgentListRailMixin now sits at AgentList.__mro__[1]); it is remaining epic work. Every other listed node fails identically at pre-epic base b9cfa7386: agent_completion (9) and directive_completion (2) %tab items already on sase-1bc notes; axe_run_agent_exec_repeat_env (6, sase-1bc.5 agent_meta) and session_root_tab marker site recorded as DISCOVERED ISSUE on sase-1bc; marker-path audit -> new ci task sase-1by; header half-page scroll +1 on sase-1b8; prompts trash limit +1 on sase-1bq; completion snapshot/kind coverage are the sase-18s cluster; the tab-scope ImportError, contract manifest, and zsh smoke nodes now pass. Remaining epic work found by the plan-vs-code audit goes to a tale: banner 2-char hint width, single rail title builder, amber Stopped rail banner bar, expanded badge reorder, spacer fallback traces, bindings.py label, stale docs/docstrings, and missing tests.

[2026-09-28T05:23:41Z · sase-1bn.land] DISCOVERED ISSUE (sase-1bn.land tale, sase_10 workspace): after `just install` rebuilt sase_core_rs from linked sase-core HEAD cbe70f66f (2 commits past the bc71eb2 pin), tests/ace/tui/test_agent_tab_scope_honesty.py fails again (12 tests) with AttributeError: sase_core_rs does not expose binding 'build_agent_tab_catalog'. LANDING TRIAGE note #3 recorded this file as passing at master 52f7351ae, so this is a regression/staleness in this workspace's rust build, not caused by this tale's node-rail changes (none of which touch agent_tab_index.py or the rust core). Not re-triaged further; flagging for whoever next needs a clean sase_core_rs build in this area.

[2026-09-28T06:20:27Z · sase-1bn.land] Tale plan:202609/land_agents_node_rail.md complete. Land agent's prior verification (LANDING TRIAGE note): all 7 epic phases checked against code on master 52f7351ae; Ctrl+S rail and Z zoom both work; pre-existing failure clusters triaged (flake sase-1bz, memory sase-1bx, ci sase-1by, +1s on sase-1b8/sase-1bq, DISCOVERED ISSUE on sase-1bc) and confirmed not epic-caused.

This tale fixed the remaining epic-caused gaps found by the plan-vs-code audit:
1. tests/ace/tui/test_agent_list_watch_highlighted.py: patch the first __mro__ class that actually defines watch_highlighted (Textual's OptionList), not AgentListRailMixin.
2. Banner hint/mark chip width: compute cell_len(chip_text) instead of a hard-coded 4 cells, fixing 2-char-hint overrun; added exhaustive width-exact tests across all 7 buckets + a wide-char label, chip/no-chip, 0/1/2-char hints, for both BY_STATUS L0 and BY_MACHINE L1 banners; replaced the tautological rail/banner-glyph-parity test with a real render+style assertion.
3. Rail "Stopped" banner: lead_style stays on the lead cell only; rule/fold-mark/count now use a foreground-only style derived from the lead (background color becomes the new foreground when the lead has one), so the folded/expanded Stopped banner no longer paints as a solid amber bar. Added tests asserting exactly one background-carrying cell and #FFAF00 foreground on the rule.
4. Expanded-row badge order: row_kind_glyph's top-level type badge (e.g. workflow's "≡") now renders after the hidden icon/retry badge/machine chip again (pre-55e4bf73b order), while monitor/gate/named-proc glyphs and all tree-row glyphs still render early. Added a hidden+retry+machine-chip regression test.
5. _try_patch_agent_row: deleted the agent_panel_border_title fallback; _agent_panel_title/_set_agent_panel_title (from PanelCollectionMixin, always present on the real app) are now the only title path. Added matching type stubs to PanelPatchMixin (mirroring PanelRefreshStateMixin's pattern) to keep mypy green now that the calls are direct instead of getattr-guarded.
6. Spacer rows: _rail_cells_for_option now recognises `spacer:`-prefixed option ids and returns blank cells directly, so spacer rows no longer hit the inconsistent-maps fallback or emit rail_fallback trace events. Added a trace-capturing regression test.
7. Labels/docstrings/docs: bindings.py Ctrl+S description -> "Toggle Node Rail"; rail/hidden wording in _agent_detail_deck_layout.py, decks/layout.py, _deck_layout_actions.py docstrings; renamed test_zoom_from_single_keeps_panel_and_collapses -> test_zoom_from_single_keeps_panel_and_hides_sidebar; docs/ace.md "Agents Zoom and Node Rail" section: dropped stale "collapse"/"no spine" wording, "node-rail preference" wording, and added the rail anatomy paragraph (pip cell, container counts, tree guides, folded-banner layout).
8. Missing tests: test_sidebar_mode_table gained RAIL+split and HIDDEN-from-RAIL+split rows; added a real-app pilot test (test_zoom_then_split_key_clears_hidden_class_and_shows_container) covering EXPANDED -> Z -> backslash; strengthened test_rail_preserves_row_positions_and_scroll to scroll to a non-zero offset (small viewport) and assert scroll offset, highlighted index, and line position are unchanged across the Ctrl+S toggle.

Verification: `just fmt` clean. `sase tool run check` (tool-run fa921e6d677f9b93cad1f11e9da319d2) escalated to the full suite (core-identity-changed) and triaged verdict no_new_failures - 25 KNOWN + 1 FLAKY, exit 1 only because of the check recipe's separate core-floor-probe stage, which is unrelated pre-existing environment breakage in this workspace (sase-core-rs 0.35.0/0.35.1 here is missing 11 capabilities such as build_agent_tab_catalog, managed_tmp_roots_*, launch_scratch_liveness_*, tool_run_* that belong to other epics entirely, none published in a release tag yet); recorded as a DISCOVERED ISSUE note on this bead and independently corroborated on sase-x5 (broad PNG/CI drift backlog) separately for the visual-golden hal

… and 718 more characters

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1bn.1](sase-1bn.1.md) | Three sidebar modes and the zoom state fixes | ✓ closed | medium | 2026-09-27 | 1 | 1 |
| [sase-1bn.2](sase-1bn.2.md) | Pure node-rail vocabulary module | ✓ closed | medium | 2026-09-27 | 1 | 1 |
| [sase-1bn.3](sase-1bn.3.md) | Paint-time rail projection inside AgentList | ✓ closed | medium | 2026-09-27 | 1 | 1 |
| [sase-1bn.4](sase-1bn.4.md) | Structural zoom chrome on the zoomed deck panel | ✓ closed | medium | 2026-09-27 | 1 | 1 |
| [sase-1bn.5](sase-1bn.5.md) | Wire the rail into the Agents tab and delete NodeSpine | ✓ closed | medium | 2026-09-27 | 1 | 1 |
| [sase-1bn.6](sase-1bn.6.md) | Align expanded status banners with the rail glyphs | ✓ closed | small | 2026-09-27 | 1 | 1 |
| [sase-1bn.7](sase-1bn.7.md) | Info-row, footer, tooltip, help, palette, and docs affordances | ✓ closed | medium | 2026-09-27 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1bn: Agents node rail and unmistakable deck zoom [closed]"]
    n1["sase-1bn.1: Three sidebar modes and the zoom state fixes [closed]"]
    n2["sase-1bn.2: Pure node-rail vocabulary module [closed]"]
    n3["sase-1bn.3: Paint-time rail projection inside AgentList [closed]"]
    n4["sase-1bn.4: Structural zoom chrome on the zoomed deck panel [closed]"]
    n5["sase-1bn.5: Wire the rail into the Agents tab and delete NodeSpine [closed]"]
    n6["sase-1bn.6: Align expanded status banners with the rail glyphs [closed]"]
    n7["sase-1bn.7: Info-row, footer, tooltip, help, palette, and docs affordances [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n1 -.-> n4
    n1 -.-> n5
    n2 -.-> n3
    n2 -.-> n6
    n3 -.-> n5
    n4 -.-> n7
    n5 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bn.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bn.1.md) | [sase-1bn.1](sase-1bn.1.md) | 1 |
| [bbugyi200.apollo.sase-1bn.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bn.2.md) | [sase-1bn.2](sase-1bn.2.md) | 1 |
| [bbugyi200.apollo.sase-1bn.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bn.3/README.md) | [sase-1bn.3](sase-1bn.3.md) | 1 |
| [bbugyi200.apollo.sase-1bn.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bn.4.md) | [sase-1bn.4](sase-1bn.4.md) | 1 |
| [bbugyi200.apollo.sase-1bn.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bn.5/README.md) | [sase-1bn.5](sase-1bn.5.md) | 1 |
| [bbugyi200.apollo.sase-1bn.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bn.6/README.md) | [sase-1bn.6](sase-1bn.6.md) | 1 |
| [bbugyi200.apollo.sase-1bn.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bn.7.md) | [sase-1bn.7](sase-1bn.7.md) | 1 |
| [bbugyi200.apollo.sase-1bn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bn.land.md) | [sase-1bn](README.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`55e4bf7`](https://github.com/sase-org/sase/commit/55e4bf73b27bc7d3b4eecb4e1e7d75ddd85f5337) | fix(ace-tui): correct rail module panel-titles import path (sase-1bn.2) | [sase-1bn.2](sase-1bn.2.md) | 2026-09-27 18:25:29 EDT |
| sase | [`42bb50a`](https://github.com/sase-org/sase/commit/42bb50a80c7a5d25e3d8e49e4a2279ba775b120f) | feat(ace): three sidebar modes with zoom state fixes (sase-1bn.1) | [sase-1bn.1](sase-1bn.1.md) | 2026-09-27 18:42:27 EDT |
| sase | [`74d1ab8`](https://github.com/sase-org/sase/commit/74d1ab8e1a995c0f6933ae41d7d1a0ba0c4ba1d7) | feat(ace-tui): align expanded status banners with rail glyphs (sase-1bn.6) | [sase-1bn.6](sase-1bn.6.md) | 2026-09-27 19:05:23 EDT |
| sase | [`f4cfc51`](https://github.com/sase-org/sase/commit/f4cfc51d701a1a459642b12870471a2d4a8d33a0) | feat(ace-tui): paint-time node rail projection inside AgentList (sase-1bn.3) | [sase-1bn.3](sase-1bn.3.md) | 2026-09-27 19:20:47 EDT |
| sase | [`0a24cf8`](https://github.com/sase-org/sase/commit/0a24cf8024983c0bca74abd2956507ffd9b253c8) | feat(ace): structural zoom chrome on zoomed deck panel (sase-1bn.4) | [sase-1bn.4](sase-1bn.4.md) | 2026-09-27 19:24:24 EDT |
| sase | [`2f03e50`](https://github.com/sase-org/sase/commit/2f03e5059b09cbefab5abce55bc94441a9f2fc98) | feat(ace-tui): project tribe lists at fixed 9-cell rail width | [sase-1bn.5](sase-1bn.5.md) | 2026-09-27 21:29:59 EDT |
| sase | [`52f7351`](https://github.com/sase-org/sase/commit/52f7351ae8afc8d088f52646425cc2bd93013945) | feat(ace-tui): mode affordances for node rail and deck zoom (sase-1bn.7) | [sase-1bn.7](sase-1bn.7.md) | 2026-09-27 23:24:17 EDT |
| sase | [`f176ada`](https://github.com/sase-org/sase/commit/f176ada71dd677e2d3fdc669d16065b3e5b232a9) | fix(ace-tui): land the remaining node-rail epic gaps (sase-1bn) | [sase-1bn](README.md) | 2026-09-28 02:26:40 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1b2.land][1] | Route symvision unused publics in _agent_list_render_rail.py found after closing sase-1b2 | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1b2.land/README.md

<!-- sase:referenced-by:end -->
