# Bead: sase-12z.5 — Finish screenshot-maintenance landing integration

[Bead Pages](../README.md) / [sase-12z](README.md) / sase-12z.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-12z.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-12z.land.md) · **Assignee:** `sase-12z.5.land`
**Created:** 2026-09-18 20:31:30 EDT · **Closed:** 2026-09-20 12:34:53 EDT
**Plan:** [202609/finish\_screenshot\_maintenance.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_screenshot_maintenance.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/finish_screenshot_maintenance.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | [bead:sase-149][2] | Epic sase-12z.5 (commit 9a56fc129) fixed the identical Textual handler-name bug on AgentDetailPanelMixin with @on(LLMCallsVisibilityChanged) and added a dispatch regression test; copy that fix and its test shape here. |
| related | [bead:sase-14a][3] | Epic sase-12z.5 worked around this in tests/ace/tui/visual/_ace_agents_png_snapshot_helpers.py (choose_agent_metadata_view refreshes the info panel); remove that workaround once the picker dismiss callback refreshes the hint. |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/finish_screenshot_maintenance.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-149/README.md
[3]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-14a/README.md

<!-- sase:links:end -->

## Description

The canonical finalizer guidance commits every dirty screenshot golden and labels unrelated golden updates, while the full ACE and pager visual corpus passes against the post-epic metadata-only Agents detail default with every intentional golden change reviewed.

## Notes

[2026-09-20T16:34:53Z · sase-12z.5.land] Verified both phases against the source and commits, integrated the epic with everything
that landed underneath it, and proved the whole visual corpus clean at master 624a29ea7.

PHASE VERIFICATION
- sase-12z.5.1 (commit 3538713c0): src/sase/xprompts/skills/sase_final.md now requires
  every dirty ACE or pager screenshot golden in the repository's commit, requires
  inspecting unrelated golden updates rather than discarding or deferring them, requires
  the exact trailer UNRELATED_SCREENSHOT_UPDATES=<reason> when they are genuinely
  unrelated, and states no trailer is needed when the screenshots are part of the
  commit's work. Both the direct-source test (tests/test_xprompt_skill_sources.py) and
  the packaged/rendered-skill test (tests/main/test_init_skills_source_content.py) pin
  the requirement and the exact trailer syntax; I ran them and they pass. The rule is
  already load-bearing: commit 9a56fc129 carries
  SASE_UNRELATED_SCREENSHOT_UPDATES=... (src/sase/workflows/commit/runtime_tags.py
  renders every footer key with the SASE_ prefix, so the canonical spelling in the skill
  is correct). `sase skill init --diff` is empty at HEAD, so the deployed provider
  copies already match this landed source; no deploy was needed.
- sase-12z.5.2 (commit 9a56fc129): confirmed in the source, not just the report. The
  File-panel, LLM Calls and slow-tool visual flows select their layout through the public
  view picker; AgentDetailPanelMixin.on_llm_calls_visibility_changed now carries
  @on(LLMCallsVisibilityChanged) (Textual derives on_llmcalls_visibility_changed, so the
  naming convention alone never dispatched it); _display_panel_widgets.py adds
  _panel_paint_key / _panel_agents_match so a panel repaints when row content, jump
  hints, marks or fold state change under unchanged row identities, with
  AgentList._panel_paint_key cleared on every other repaint path. The 27 regression tests
  in tests/ace/tui/test_agent_display_diff.py and tests/ace/tui/test_agent_view_picker.py
  pass.

INTEGRATION (the work this landing added)
The phase-2 commit was rebased over 14 commits that landed during its run, and two of
them changed rendered TUI output without refreshing goldens, so the corpus was red again
by the time I started:
- A complete `just test-visual` at 624a29ea7 reported created=0 updated=19 unchanged=690.
- 18 of those trace to sase-11y.7 (92dd554c4), which changed _TAB_COLORS['axe'] in
  src/sase/ace/tui/widgets/tab_bar.py from #FF5F5F to #00D7AF and reworded the '!x' help
  binding. I reviewed both update groups against expected/actual captures, confirmed the
  only differences are that intended accent change and the reworded binding, and
  refreshed all 18 (16 axe_*, help_keymaps_changespecs, link_rail_axe_twelve_links).
  A DISCOVERED ISSUE note records this on sase-11y.
- The 19th, agents_fleet_remote_tribe_families_120x40, was deliberately NOT accepted. It
  drifted in three consecutive runs under host load and was unchanged in three later runs
  on a quieter host, and the drift still reproduced with this epic's source changes
  reverted. The failing capture picks up live neighbor and active-agent state its
  fixtures cannot produce. Filed as task sase-14b and noted on sase-133.5.
- Final verification: a complete `just test-visual` is 972 passed / 1 skipped,
  mode/status check/clean, created=0 updated=0 unchanged=709 stale=0, complete inventory,
  golden tree unchanged (run bf19406b11e045dc90fca08da41a912e).
- Three task beads filed by agents on pre-9a56fc129 trees are resolved or partly resolved
  by this epic; I recorded the evidence on each rather than closing them, because each
  also carries a signature my athena run cannot rule out: sase-13y (five external/linked
  repo and LLM Calls nodes; apollo-only, links sase-13u path truncation), sase-13v (two
  fakey retry e2e nodes; a separate 491-pixel detached-worktree signature), sase-144
  (toast determinism; also names undiagnosed config_center_logs_tab goldens).

FOLLOW-UPS (every PROPOSED FOLLOW-UP from both children)
- Zoom panel modal's dead LLMCallsVisibilityChanged handler: verified still present at
  src/sase/ace/tui/modals/zoom_panel_modal.py:345 -> new task sase-149 (small, bug),
  linked to this epic.
- Agents header view hint stale on a no-change or Esc picker dismiss -> new task sase-14a
  (small, bug), linked to this epic.
- agents_fleet_remote_tribe_families visual flake (plus the unmitigated
  KeybindingStatusMixin._update_status auto-width cache) -> new task sase-14b (large,
  flake), linked to sase-119, sase-12a and sase-144.
- Stale test-cost hard budgets (subprocess_run.count 52000 below every retained athena
  recording, parser_create.cpu 68 tripping at 86.4): confirmed still uncalibrated in
  tests/perf/baselines/test_cost_budgets.json at HEAD -> corroborated existing task
  sase-xc with a +1 rather than filing a duplicate.
- Full-lane transient failures from sase-12z.5.1 -> corroborated sase-12f
  (monitor capacity delayed child bootstrap) and sase-13c (AcePage reset-hook leaks) with
  +1s; both passed on focused rerun on an unchanged, documentation-only tree.
- The sase-12z.5.2 note about the pre-rebase base failing just check on 20 mypy errors in
  ace_tmux*.py and 13 private-import symvision symbols is resolved: 86ff62c08 and
  45df42549 landed those fixes and both gates are green at HEAD.
- Declined to file anything for the sase-12z.1 completion-spec ordering and sase-12z.4
  sidecar clone-staging proposals: the epic plan's landing audit already recorded both as
  fixed by later work, and this landing did not contradict that.

VERIFICATION STATE
`sase tool run check` at HEAD passes fmt, keep-sorted, ruff, mypy, feature flags,
pyscripts, test waits, changelog and terminology, and fails only at lint (symvision) on
26 unused public symbols in src/sase/sdd/_store_clone_*.py,
src/sase/ace/tui/models/_agent_runner_slot_capacity.py, src/sase/service/host_*.py and
src/sase/completion/runtime_cache_generation.py. That failure is byte-identical on the
unmodified tree before my change (this landing touches only PNG goldens) and is already
tracked as sase-13s, which I corroborated with a +1. `sase bead epic-symbols sase-12z.5`
reports no entries. `just check-full` was not run: this prompt did not instruct it.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12z.5.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-12z.5.land/README.md) | [sase-12z.5](sase-12z.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1d3bef8`](https://github.com/sase-org/sase/commit/1d3bef89414d940fee072b4d7d81318f5109715d) | fix(visual): refresh the Services-tab goldens left stale during sase-12z.5 | [sase-12z.5](sase-12z.5.md) | 2026-09-20 12:42:28 EDT |
| sase--plans | [`sase--plans@ae49a4c`](https://github.com/sase-org/sase--plans/commit/ae49a4c309ddd5ab1405050ff8aff511622dee2c) | docs(plans): mark the screenshot-maintenance plans done | [sase-12z.5](sase-12z.5.md) | 2026-09-20 12:43:24 EDT |
