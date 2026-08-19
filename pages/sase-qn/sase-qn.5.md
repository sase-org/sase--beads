# Bead: sase-qn.5 — Enforce the budgets and close out the epic

[Bead Pages](../README.md) / [sase-qn](README.md) / sase-qn.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.075](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.075.md) · **Assignee:** `sase-qn.5` · **Size:** small
**Created:** 2026-08-18 20:12:40 EDT · **Closed:** 2026-08-18 22:58:55 EDT
**Plan:** [202608/plugin\_catalog\_scale.md](https://github.com/sase-org/sase--plans/blob/main/202608/plugin_catalog_scale.md)

## Description

guard: flip the recorded baselines into enforced budgets, add the regression check alongside the other perf guards, verify the combined tree with check-full, and reconcile any feature flag opened during the epic.

## Notes

[2026-08-19T02:09:26Z · sase-qn.5] Feature flag plugin_catalog_scoped_latest (sase-qq) stays beta, default off: flag kind is immutable after create (only remove_by thresholds are writable), so flipping the registry to sunset would fail tools/check_feature_flags with kind_mismatch. The scoped O(installed) path is implemented, both-states tested, and the regression checker enforces that curve. Default remains full-eager until FlagTriage converts or removes the flag.

[2026-08-19T02:09:41Z · sase-qn.5] PROPOSED FOLLOW-UP: convert plugin_catalog_scoped_latest from beta to sunset so scoped eager enrichment is default-on — kind cannot be changed on sase-qq after create, and this phase cannot flip the registry without a kind_mismatch.

[2026-08-19T02:21:04Z · sase-qn.5] Fixed a combined-tree bug from the tui/enrich seam: _apply_plugin_latest now updates _plugin_entry_by_name so lazy highlighted-row latest does not leave _entry_by_name stale. Verified tests/ace/tui/test_plugins_browser_pane_detail.py::test_plugins_pane_lazy_fetches_highlighted_latest_when_flag_on.

[2026-08-19T02:31:10Z · sase-qn.5] PROPOSED FOLLOW-UP: flake — tests/ace/tui/test_plugins_browser_pane_sase_update.py::test_updates_pane_sase_update_confirm_executes_and_refreshes timed out wait_for() after 5s under the escalated 14-worker just check suite; serial isolated rerun passed in 1.33s. Unrelated to catalog-scale guards (catalog stubbed). Also noted on sase-qn.3.

[2026-08-19T02:31:28Z · sase-qn.5] PROPOSED FOLLOW-UP: flake — tests/test_ace_testing.py::test_ace_page_fast_startup_is_structurally_quiet left a cancelled pump-free task sase-artifacts-project-choices under the escalated suite; serial isolated rerun passed. Unrelated to this phase; also noted on sase-qn.1.

[2026-08-19T02:57:40Z · sase-qn.5--1] PROPOSED FOLLOW-UP: flake — tests/ace/tui/modals/test_project_inventory_subtabs.py::test_cross_navigation_and_escape_surface_disabled_workspaces exceeds flake baseline (3 eligible full-run fails after 2026-08-15, dirty trees on sase_12/sase_13). Serial isolated rerun passed in 0.55s. Unrelated to catalog-scale guards. Land agent: file a flake bead and add the node to tests/reproducible_flake_baseline.txt.

[2026-08-19T02:57:56Z · sase-qn.5--1] PROPOSED FOLLOW-UP: flake — tests/ace/tui/modals/test_snippet_name_modal.py::test_new_trigger_returns_empty_starting_body exceeds flake baseline (eligible fail 2026-08-18T23:51 clean tree on sase_12, plus earlier dirty runs). Serial isolated rerun passed in 0.38s. Unrelated to this phase. Land agent: file a flake bead and add the node to the baseline.

[2026-08-19T02:58:12Z · sase-qn.5--1] PROPOSED FOLLOW-UP: flake — tests/ace/tui/test_commits_pane_interactions.py::test_commits_pilot_drives_live_filter_bar_detail_copy_and_toggles exceeds flake baseline (eligible fails through 2026-08-18 on sase_15/sase_18). Serial isolated rerun passed in 4.26s. Unrelated to catalog-scale guards. Land agent: file a flake bead and add the node to the baseline.

[2026-08-19T02:58:27Z · sase-qn.5--1] PROPOSED FOLLOW-UP: flake — tests/ace/tui/test_plugins_browser_pane_detail.py::test_plugins_pane_lazy_fetches_highlighted_latest_when_flag_on exceeds flake baseline. This tree failed it at 02:18 before the identity-map fix; after _apply_plugin_latest updates _plugin_entry_by_name it passed this check-full test-cost run and a serial isolated rerun (1.15s). Still failed later on unrelated sase_15 trees (including one clean). Not a remaining phase regression. Land agent: file a flake bead and add the node to the baseline.

[2026-08-19T02:58:55Z · sase-qn.5--1] Verified plugin catalog scale budgets: budgets_enforced=true; n=2000 filter_keystroke p95=11.012ms and j_press p95=0.495ms stay under 16ms; enrich scan_work=0 and fetch_calls=5 (O(installed)) at n=1000/2000; unsplittable over-cap fetch warns instead of silently dropping. plugin-catalog-scale-check and the CI perf-floors step are wired. plugin_catalog_scoped_latest stays beta/default-off (kind is immutable after create; follow-up recorded to convert to sunset). Identity-map fix: _apply_plugin_latest updates _plugin_entry_by_name so lazy highlighted-row latest is visible via _entry_by_name. just check-full: every lint gate and test-cost (full suite) green; failed only on the flake baseline gate — 4 host-wide historical flakes not in tests/reproducible_flake_baseline.txt (serial isolated reruns all passed; recorded as PROPOSED FOLLOW-UP for flake beads). No --epic-symbol leftovers.

[2026-08-19T03:00:57Z · sase-qn.5--1] Enforced 16 ms filter/j p95 at n=2000 (filter 11.012 ms, j 0.495 ms); O(installed) enrich (scan_work=0, fetch_calls=5) and unsplittable over-cap fetch warns instead of silently dropping; just plugin-catalog-scale-check plus CI perf-floors step; plugin_catalog_scoped_latest stays beta/default-off (kind immutable; follow-up to convert); _apply_plugin_latest updates _plugin_entry_by_name so lazy highlighted-row latest is visible; just check-full lint+test-cost green, flake-baseline red on 4 host-wide historical flakes (serial isolated reruns passed, including lazy-latest after identity-map fix).

## Dependencies

- **Depends on:** [sase-qn.1](sase-qn.1.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-qn.2](sase-qn.2.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-qn.3](sase-qn.3.md) ✓ · ⧖ 2026-08-18
- **Depends on:** [sase-qn.4](sase-qn.4.md) ✓ · ⧖ 2026-08-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qn.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-qn.5.md) | [sase-qn.5](sase-qn.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ce5ddf1`](https://github.com/sase-org/sase/commit/ce5ddf13cd8030b385c430da1a5909b07849a3c1) | perf(plugins): enforce catalog-scale budgets and keep lazy latest | [sase-qn.5](sase-qn.5.md) | 2026-08-18 23:02:02 EDT |
