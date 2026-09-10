# Bead: sase-z7.3 — Render and verify the compact usage window display

[Bead Pages](../README.md) / [sase-z7](README.md) / sase-z7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0hy](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0hy.md) · **Assignee:** `sase-z7.3` · **Size:** medium
**Created:** 2026-09-10 07:06:09 EDT · **Closed:** 2026-09-10 16:15:58 EDT
**Plan:** [202609/usage\_window\_indicators.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_window_indicators.md)

## Description

compact-display: implement icon badges, countdowns, ten-color themes, bounded layout, accessible disclosure, integration tests, and visual verification.

## Notes

[2026-09-10T19:17:39Z · sase-z7.3--3] PROPOSED FOLLOW-UP: master just check is red repo-wide on the feature-flag gate — commit a8d99d295 (sase-yy.6 artifact-link cutover) deleted the link_events registry definition but left flag bead sase-z0 open, so tools/check_feature_flags rule 8 now errors ("live flag bead sase-z0 has no definition") for every agent; close sase-z0 or restore its definition.

[2026-09-10T20:14:51Z · sase-z7.3--4] PROPOSED FOLLOW-UP: master is red on 8 weighted-capacity/runner-slot tests independent of sase-z7 — tests/test_fleet_contract_sase_core_rs.py (KeyError queue_weight), tests/ace/tui/test_agent_runner_slots.py (3, queue ordering + fractional capacity), tests/test_core_agent_scan_options.py (2, capacity_only round-trip), tests/test_agent_wait_live.py, tests/test_agent_list_runner_slots.py; proven pre-existing by stashing all sase-z7.3 changes and re-running at HEAD abdcb86d6 (identical 8 failures), so the installed sase-core-rs 0.33.0 binding is out of step with the Python callers; origin/master is 4 commits ahead touching exactly src/sase/ace/tui/models/agent_runner_slots.py, src/sase/core/runner_slots/_admission.py and tools/check_sase_core_rs_bindings, so rebasing may resolve it.

[2026-09-10T20:15:21Z · sase-z7.3--4] PROPOSED FOLLOW-UP: the ACE PNG visual suite is broadly red on master for the same weighted-capacity mismatch — the agents state strip now renders "0.0/10.0" where the committed goldens expect the old capacity text, so ~40 of 49 agents-pane snapshots in a fixed 12-file subset fail on ~0.48% of pixels confined to that one row; proven unrelated to sase-z7.3 by running the identical subset with and without the phase changes (byte-identical 40-failure sets, 9 passed both ways) and it also reproduces with everything stashed at HEAD; needs the core binding fixed first, then one deliberate golden regeneration — do NOT bulk-accept these goldens while the binding is still mismatched.

[2026-09-10T20:15:58Z · sase-z7.3--4] Compact usage-window display complete and verified. Implementation (earlier family members): _provider_usage_indicator.py consumes ProviderUsageIndicatorProjection from cached_usage_indicator_projection(); new _usage_indicator_palette.py (ten-bucket dark/light palette) and _usage_indicator_format.py (countdown/percent/specifier); provider_disables_indicator.py caches UsageBadge tuples, repaints on theme change, caps usage at half the top bar; dead indicator_usage_items/indicator_usage_attention removed and CapacityHint/UsagePeekSnapshot/cached_usage_display_snapshot privatized per symvision; docs/ace.md updated. This turn closed the plan step-7 visual gap: added tests/ace/tui/visual/_provider_usage_indicator_fixtures.py plus test_ace_png_snapshots_provider_usage_indicator_states.py with 8 new goldens — 160-col three weekly badges in full, Claude session+weekly+weekly-Fable, 60-col crowded degrading to the "usage 3" count rung beside routing controls, stale ~ / reset-passed ?%+glyph / unknown-reset ?, collector-failure warning marker, ten-bucket palette in dark AND light themes (all 10 deciles distinct), and an unobserved provider contributing no phantom badge. Every new PNG was opened and visually inspected, not just exit-code checked; the two pre-existing goldens still pass byte-identical after the fixtures refactor. VERIFIED: ruff format clean tree-wide, ruff check clean, mypy clean (4289 + 49 files), symvision clean, keep-sorted/pyscripts/test-waits/toobig clean, prettier clean, contract manifest passes (no new-file registration needed), epic-symbols empty, usage visual lane 10/10 passed, tests/llm_provider + provider presentation/disables 915 passed, tests/ace/tui non-visual 2960 passed. NOT green and NOT caused by this phase: just _lint-flags (pre-existing sase-z0 link_events registry gap) and 8 weighted-capacity/runner-slot test failures plus the broad agents-pane PNG suite, all proven pre-existing by stashing every sase-z7.3 change and reproducing identically at HEAD abdcb86d6 — recorded as three PROPOSED FOLLOW-UP notes.

## Dependencies

- **Depends on:** [sase-z7.1](sase-z7.1.md) ✓ · ⧖ 2026-09-10
- **Depends on:** [sase-z7.2](sase-z7.2.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z7.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z7.3.md) | [sase-z7.3](sase-z7.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1ef9c09`](https://github.com/sase-org/sase/commit/1ef9c092e35cdeba38fed1fa76799dc661d15295) | feat(ace): render compact provider usage window badges | [sase-z7.3](sase-z7.3.md) | 2026-09-10 16:17:34 EDT |
