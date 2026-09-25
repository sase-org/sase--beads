# Bead: sase-17m.5.1.5 — Snapshot renames, perf check, and classification sweep

[Bead Pages](../README.md) / [sase-17m.5.1](sase-17m.5.1.md) / sase-17m.5.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-17m.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-17m.5.md) · **Assignee:** `sase-17m.5.1.5` · **Size:** medium
**Created:** 2026-09-25 00:06:06 EDT · **Closed:** 2026-09-25 04:03:13 EDT
**Plan:** [202609/agent\_session\_ace\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_session_ace_cutover.md)

## Description

snapshots-sweep: rename the family-named PNG snapshot tests, fixture modules, and goldens, and every remaining family-named tests/ace or tests/perf file. Update the shard-timing and flake baselines. Run a full just fix-tui-screenshots through /sase_monitor, inspect the report, and remove stale goldens only after the full run. Run the j/k navigation benchmark to confirm no regression. Classify every remaining famil hit in ACE scope, record hand-offs on sase-17m.5, and run sase tool run check.

## Notes

[2026-09-25T07:55:53Z · sase-17m.5.1.5] PROPOSED FOLLOW-UP: visual test test_agent_session_panel_fold_levels_and_member_override_png_snapshots fails scrolling to Main section anchor agent-xprompt (15s timeout); reproduces identically on clean base tree, so pre-existing (likely copy-phase prompt-panel fallout). Blocks pixel-proof of 3 renamed goldens: agents_session_panel_level_2, agents_session_conversation_level_1/2.

[2026-09-25T07:56:11Z · sase-17m.5.1.5] PROPOSED FOLLOW-UP: visual convergence flakes on loaded host (pending_workers=_load 30s timeouts, zero pixel drift): test_ace_png_snapshots_command_line.py (up to 8 nodes, churning set), clan_panel swarm test, provider_usage attention/crowded tests; all reproduce on clean base tree in the same timeout mode. Full-suite run: 1023 passed / 13 failed+2 errors (errors were copy-phase stragglers, fixed in-phase).

[2026-09-25T07:56:21Z · sase-17m.5.1.5] PROPOSED FOLLOW-UP: j/k benches miss p95 budgets under shared-host load with 300ms+ max outliers (clan 17-28ms vs 16 budget; tribe p50~46-50/p95~68-82 vs 40; fleet p50~12-15/p95~24-35 vs 16; axe also over) across 2 runs; view-hints regression check fully green incl unfolded-session press 1.9ms vs 85.4ms baseline. Phase changed zero src files so no attributable regression; benches need a quiet-host re-run before landing.

[2026-09-25T07:56:37Z · sase-17m.5.1.5] PROPOSED FOLLOW-UP: remaining agent-session-concept test identifiers from earlier phases untouched (file scope honored): ~90 test_*family* fn names across tests/ace (family_container/family shell/family row/sort-and-reorder), _family() helper in tests/ace/tui/_agent_enter_targets_helpers.py, loader docstring prose (family rows/agent-family context in artifact_reads/bead_touches/glossary_reads/memory_reads/skill_uses/opened_workspaces), and on-disk family= keys in tests/ace/tui/owner_roster_fixture.py (needs persisted-shape ruling: runtime vs ACE ownership). Unrelated meanings (model_family, Patch revert family, vcs/operator/marker/vim/provider families, font families) and test-local opaque data (family-test, visual-family*) stay by design.

[2026-09-25T08:02:26Z · sase-17m.5.1.5] PROPOSED FOLLOW-UP: sase tool run check red only at SASE validation / init memory --check (sase/memory/README.md +2/-2 drift); fails identically (exit 1) on clean base tree. All lint gates green (ruff, mypy, symvision, keep-sorted, fmt, flags).

[2026-09-25T08:03:13Z · sase-17m.5.1.5] snapshots-sweep done. Renamed 7 test/fixture files (4 PNG snapshot tests families/family_panel+gate+monitor, 2 fixture modules, fleet family_tree test) to agent_session naming, 25 PNG goldens family/families->session/sessions via git mv, updated snapshot ids/imports/fixture+test identifiers/titles in 11 visual+fleet files (rendered fixture data kept, pixels identical). Re-keyed stale shard_timings roster entry; perf baselines had no family refs. Fixed 4 copy-phase straggler test files that failed to import (shell_section, identity_header_compact + 2 helper-pattern files). Full just fix-tui-screenshots --check: 1023 passed; accepted 5 proven updates (titles + SESSION/SHELL copy the copy phase missed) after inspecting each diff (pixel-localized, expected class); 25 renamed goldens verified pixel-identical. Remaining failures all reproduce identically on base (filed as follow-ups): panel fold-levels scroll-anchor timeout, command_line/clan/provider convergence flakes, memory README drift. Perf: view-hints check 12/12 PASS (unfolded session press 1.9ms vs 85.4 baseline); j/k p95s miss budgets under host load (clan p95 ~17-28 vs 16, tribe p50 ~46-50/p95 ~68-82 vs 40, fleet p50 ~12-15/p95 ~24-35 vs 16, 300ms+ max outliers) with zero src changes in phase. Lint gates all green (ruff/mypy/symvision); epic-symbols clean.

## Dependencies

- **Depends on:** [sase-17m.5.1.4](sase-17m.5.1.4.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-17m.5.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-17m.5.1.5/README.md) | [sase-17m.5.1.5](sase-17m.5.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e9ba5b7`](https://github.com/sase-org/sase/commit/e9ba5b708adec9ba795971289e6fae7d5e048984) | refactor(ace-tui): rename family test naming to agent-session across snapshots and fixtures | [sase-17m.5.1.5](sase-17m.5.1.5.md) | 2026-09-25 04:05:20 EDT |
