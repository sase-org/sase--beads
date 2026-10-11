# Bead: sase-1jy.2 — Remove superlinear and redundant work from WaitDependencyIndex.add\_many

[Bead Pages](../README.md) / [sase-1jy](README.md) / sase-1jy.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0zo](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0zo.md) · **Assignee:** `sase-1jy.2` · **Size:** medium
**Created:** 2026-10-11 11:18:31 EDT · **Closed:** 2026-10-11 12:52:43 EDT
**Plan:** [202610/wait\_checks\_scoped\_view.md](https://github.com/sase-org/sase--plans/blob/main/202610/wait_checks_scoped_view.md)

## Description

batch-index-build: refresh effective clan tribes once per touched clan generation, invalidate query caches once per batch, and skip plan_path.json reads that cannot matter, with a parity test proving batch and sequential adds build identical indexes.

## Notes

[2026-10-11T16:50:59Z · sase-1jy.2] batch-index-build measurement: BEFORE (plan profile, athena load ~13, 17870 rows): add_many 2.9s incl. 9757x _refresh_effective_clan_tribe ~1.0s, 17870x plan_path.json opens ~0.43s, 2x done.json stats/row, 1x cache-invalidate/row. AFTER (this phase): 500-row _add_prepared loop 0.079s (~0.16ms/row); full 17896-row add_many 63s wall under load 18-40 dominated by dismissed-bundle SQLite first-connection init (~19.6s, environmental). Unit proof: tribe refreshes=touched generations only (4 vs 20 rows), plan_path reads=3 vs 20 rows, done.json stats N vs 2N, invalidates 1 vs N. Parity tests 4/4 pass.

[2026-10-11T16:51:16Z · sase-1jy.2] PROPOSED FOLLOW-UP: test_tui_app_import_stays_under_startup_budget fails identically on clean base (3516 modules vs 3513 cap) — needs budget bump plus tools/tui_import_closure attribution

[2026-10-11T16:51:21Z · sase-1jy.2] PROPOSED FOLLOW-UP: full-check timing flakes under host load 30-40 (test_sdd_git_identity_survives_empty_home_subprocess, test_commit_view_modal_toggles_plan_and_restores_cached_diff, test_alias_sbd_completes_static_bead_tree, test_weight_two_land_agent_session_retains_one_claim) all pass in isolation on base — consider quarantine or load-aware timeouts

[2026-10-11T16:52:43Z · sase-1jy.2] Batch add_many now refreshes each touched clan generation once, invalidates query caches once per batch, carries done.json existence (N vs 2N stats), and skips plan_path.json reads unless meta preconditions hold. Verified: 4/4 new parity tests pass (batch==sequential over clans/generations/recorded-tribe/posthoc/planners/queued-parked/archived corpus, plus skip-count and refresh-count proofs); 26 wait/clan-cache tests pass; ruff+mypy clean; all just-check lint stages exit 0; marker-path audit updated (add_many site removed); 6 full-check failures triaged — 1 pre-existing import-budget fail reproduces identically on base, 4 timing flakes pass in isolation on base, 1 audit fixed by this phase. Measurements and follow-ups recorded in bead notes.

## Dependencies

- **Blocks:** [sase-1jy.3](sase-1jy.3.md) ◐ · ⧖ 2026-10-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jy.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jy.2/README.md) | [sase-1jy.2](sase-1jy.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9982db1`](https://github.com/sase-org/sase/commit/9982db19428a0b3c6239b43cc5f7b7d4eae31b07) | perf(wait-index): batch add\_many with linear clan-tribe refresh and cached plan checks | [sase-1jy.2](sase-1jy.2.md) | 2026-10-11 12:55:12 EDT |
