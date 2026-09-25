# Bead: sase-18d.7.1 — Pilot harness and clan removal race

[Bead Pages](../README.md) / [sase-18d.7](sase-18d.7.md) / sase-18d.7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-18d.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-18d.land.md) · **Assignee:** `sase-18d.7.1` · **Size:** medium
**Created:** 2026-09-24 22:00:17 EDT · **Closed:** 2026-09-24 23:51:01 EDT
**Plan:** [202609/x\_kill\_e2e\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/x_kill_e2e_completion.md)

## Description

clan_race: Drive the mounted Agents tab with on-disk agents through a clan x, an in-flight load, and fleet reprojection.

## Notes

[2026-09-25T03:50:12Z · sase-18d.7.1] PROPOSED FOLLOW-UP: 34 tests fail identically on the clean base tree (query-profile agents, completion snapshot/kind-coverage, kill-and-edit/family-relaunch prompt names, directives_bead, force-reuse seam, editor helper agent catalog, artifacts pane state) — likely fallout of the recent agent-session query dialect and agent-family removal commits; no task bead tracks them; reproduce with `uv run python -m pytest tests/test_query_profile_agents.py tests/completion tests/ace/tui/test_kill_and_edit_prompt_name.py tests/test_directives_bead.py`

[2026-09-25T03:50:25Z · sase-18d.7.1] PROPOSED FOLLOW-UP: app._agents_local_visible has no production reader and goes stale after a clan kill (_sync_agents_local_source_from_current mirrors it from _agents before _refilter_agents rebuilds it) — delete the attribute or re-sync it after the refilter; the pilot harness deliberately does not assert on it

[2026-09-25T03:50:35Z · sase-18d.7.1] Pre-existing check blockers reproduced on the clean base tree (tracked elsewhere): lint (mypy) on tools/sase_core_wheel_cache (sase-18q), lint (test waits) tests/test_sase_core_wheel_cache_tool.py:490 (sase-18r), lint (symvision) stale sase-18i epic-symbol entries (pattern tracked by sase-o7). `sase tool run check` aborts at the mypy stage, so the remaining stages were run individually.

[2026-09-25T03:51:01Z · sase-18d.7.1] Added the mounted-Agents-tab pilot harness (tests/ace/tui/_agents_x_pilot_helpers.py) and tests/ace/tui/test_agents_tab_x_clan_race_e2e.py: real AceApp, on-disk home-mode agents with real fixture process trees, real x + double confirm, the real cleanup payload run through apply_cleanup_payload_for_result on a worker thread, a load parked between worker prep and apply, real fleet refreshes, and forced complete-history reloads; clan, members and every fixture pid verified after each stage (20/20 and 12/12 repeated runs green). Mutation-checked: disabling tombstones, the reprojection filter, compute tombstones, durable termination and tree discovery each fail the pilot. It exposed an epic-caused defect (c88987e79): the proc-projection boundary rebase and the fold-level boundary rebuild stamped the live removal generation onto the worker's stale roster, blinding the apply-time recheck so a racing load re-published removed rows; fixed in _loading_compute.py/_loading_apply.py with two component regressions (test_agents_tab_removal_tombstones.py, both failing pre-fix). Test infra: launch_runner(runner_ignores_term=), suite termination guard now also targets launched runners after they die. Verification: ruff/mypy(src+tests)/keep-sorted/flags/pyscripts/changelog/terminology/validate/committed-plans green; just test-scoped = 35 failed/47124 passed where 34 failures reproduce identically on the clean base tree and 1 (zsh completion smoke) passes in isolation on both trees; sase tool run check aborts at pre-existing mypy failure in tools/sase_core_wheel_cache (sase-18q), plus baseline test-waits (sase-18r) and symvision epic-symbol failures unrelated to this change. Follow-ups noted as PROPOSED FOLLOW-UP.

## Dependencies

- **Blocks:** [sase-18d.7.2](sase-18d.7.2.md) ◐ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18d.7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18d.7.1/README.md) | [sase-18d.7.1](sase-18d.7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ae34dba`](https://github.com/sase-org/sase/commit/ae34dba2066acf114bc158de39061ba6533f189d) | test(ace): drive Agents-tab clan x through a mounted pilot and fix racing-load resurrection | [sase-18d.7.1](sase-18d.7.1.md) | 2026-09-24 23:52:25 EDT |
