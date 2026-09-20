# Bead: sase-133.5.2 — Resolve production family presentation facts

[Bead Pages](../README.md) / [sase-133.5](sase-133.5.md) / sase-133.5.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-133.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-133.land.md) · **Assignee:** `sase-133.5.2` · **Size:** large
**Created:** 2026-09-19 08:06:11 EDT · **Closed:** 2026-09-20 09:39:10 EDT
**Plan:** [202609/remote\_parity\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_parity_landing_repairs.md)

## Description

owner-facts: derive topology, rich statuses, tribe inheritance, shell facts, and runtime anchors from real owner records and consume them through the existing viewer renderer.

## Notes

[2026-09-20T12:15:21Z · sase-133.5.2] PROPOSED FOLLOW-UP: catalog reads artifact-directory timestamps as UTC — Rust parse_record_timestamp ignores the configured timezone, so rows lacking workflow_state.start_time show a start time offset by the host UTC offset

[2026-09-20T12:15:54Z · sase-133.5.2] PROPOSED FOLLOW-UP: master lint/test baseline failures unrelated to owner facts — mypy no-untyped-def in ace_tmux*.py, symvision private imports in memory/selector_models.py and main/ace_tmux_support.py, tests/test_capacity_gate_to_admission.py queue_weight

[2026-09-20T13:38:20Z · 0nz] PROPOSED FOLLOW-UP: corrects note #2 — primary-repo master is red for reasons that all predate owner facts (2631449914 touches none of these modules; items 4-6 also fail identically with its six src/ files reverted to their pre-phase revisions). Where just check stops: (1) lint (mypy), recipe _lint-mypy — 20 no-untyped-def errors in 3 files: src/sase/main/ace_tmux.py, ace_tmux_window.py, ace_tmux_session.py (tmux launcher split). Behind it, not reached by just check: (2) lint (symvision), recipe _lint-symvision — 28 unused public symbols in sdd/_store_clone_admission.py + _store_clone_remote.py (half-landed remote-clone work), service/host_support.py + host_reporting.py, ace/tui/models/_agent_runner_slot_capacity.py, ace/tui/_proc_observer_models.py, ace/tui/widgets/bgcmd_list.py, completion/runtime_cache_generation.py; note #2's private-import errors in memory/selector_models.py and main/ace_tmux_support.py are stale (fixed by 86ff62c08). Scoped test lane (just test-scoped, run directly): (3) tests/test_capacity_gate_to_admission.py, 2 failures, assert None == 2.0 on land.queue_weight (xprompt directive rendering; already in note #2). (4) NEW, deterministic, reproduced alone: tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection — tests/contract_manifest.txt omits tests/test_tool_adoption_report_tool.py, added by 9cfb06a54; fix is just refresh-contract-manifest. (5) NEW, deterministic, reproduced alone: tests/ace/tui/test_lazy_tier2_reconcile_apply.py::test_changed_query_incomplete_load_after_reconcile_rearms — _agents_seen_complete_history stays True after an incomplete load under a new query key; the test passes with the src/ change of 9231c9352 (fix(tui): stop incomplete bounded loads from replacing a larger cache) reverted, so that commit made either the test or the behavior wrong. (6) NEW, deterministic, reproduced alone: tests/ace/tui/test_app_import_budget.py — importing sase.ace.tui.app loads 3292 modules against a budget of < 3290; bisected to 3bfec5f70 (refactor(sdd): split store clone operations) — 3275 at 7b4cd80fb, 3292 both before and after 2631449914, so owner facts adds zero modules. Also seen once and not reproducible: tests/test_launch_proc_runtime.py::test_proc_dispatch_rebinds_launch_hold_and_settlement_releases_it failed under the parallel scoped run (launch hold not released) but passed alone (13 passed) — load-sensitive flake, not a baseline failure.

[2026-09-20T13:39:10Z · 0nz] Closure verification for owner presentation facts (feature commits 2631449914 primary, 92cf0ca sase-core). VERIFIED: (a) sase-core just check green at d93ecbe (92cf0ca plus release commit): fmt, clippy and full suite incl. sase_core_py binding tests, 32 test binaries, 3946 passed, 0 failed. (b) Phase oracle green on a freshly installed workspace (just install): test_owner_facts_oracle.py + test_owner_roster_oracle.py + test_fleet_contract_sase_core_rs.py = 40 passed. (c) just fix left the tree clean. NOT GREEN: primary-repo just check is RED and was not made green: it stops at lint (mypy) - recipe _lint-mypy, 20 no-untyped-def errors in 3 files (main/ace_tmux.py, ace_tmux_window.py, ace_tmux_session.py). lint (symvision) is also red (28 unused public symbols; measured directly since just check aborts before it). just test-scoped run directly: 6 failed, 43647 passed, 16 skipped. Classified: 2 = documented baseline test_capacity_gate_to_admission (assert None == 2.0 on land.queue_weight); 1 = flake (test_launch_proc_runtime, passed alone, 13 passed); 3 = real, reproduced alone, and proven independent of this phase by failing identically with its six src/ files reverted: test_contract_manifest (manifest missing test_tool_adoption_report_tool.py, from 9cfb06a54), test_lazy_tier2_reconcile_apply (9231c9352), test_app_import_budget (3292 modules vs budget 3290, bisected to 3bfec5f70; owner facts adds 0 modules). No failure traced to this phase, so no product code changed and nothing was repaired. Baseline gates left red for their owners (tmux launcher split, remote-clone/service-host/runner-slot symbols, xprompt directive rendering, the three test failures above); details in note #3, which corrects the stale note #2. No ancestor bead touched.

## Dependencies

- **Depends on:** [sase-133.5.1](sase-133.5.1.md) ✓ · ⧖ 2026-09-19
- **Blocks:** [sase-133.5.4](sase-133.5.4.md) ◐ · ⧖ 2026-09-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-133.5.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-133.5.2.md) | [sase-133.5.2](sase-133.5.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2631449`](https://github.com/sase-org/sase/commit/263144991496900af018d7470257dc841555d873) | feat(fleet): carry owner presentation facts through the viewer catalog adapter | [sase-133.5.2](sase-133.5.2.md) | 2026-09-20 08:17:33 EDT |
| sase-core | [`sase-core@92cf0ca`](https://github.com/sase-org/sase-core/commit/92cf0ca230a436a6dd48c9cd09aeb70759119404) | feat(fleet): derive owner presentation facts in core and bump contract to v5 | [sase-133.5.2](sase-133.5.2.md) | 2026-09-20 08:21:19 EDT |
