# Bead: sase-zn.9 — Finish ACE typing-lag correctness and measured acceptance

[Bead Pages](../README.md) / [sase-zn](README.md) / sase-zn.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zn.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zn.land.md) · **Assignee:** `sase-zn.9.land`
**Created:** 2026-09-12 17:29:01 EDT · **Closed:** 2026-09-14 08:22:09 EDT
**Plan:** [202609/finish\_ace\_typing\_lag.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_ace_typing_lag.md)

## Description

Repair the notification cache race and scratch pressure integration, attribute retained ACE memory, and prove the original responsiveness targets under real athena load.

## Notes

[2026-09-13T14:13:44Z · sase-zu.land] LOAD-TIERING AUDIT from sase-zu landing at 654335d555: confirmed production full-history index reads miss an artifact created after index rebuild while reporting complete_history=true and needs_full_history_reconcile=false. Full-history revalidation also scans marker signatures across matching tiers before candidate filtering, and active search disables exact delta updates. The sase-zu remaining-work child will own indexed history completeness, bounded revalidation, query-key reuse and production-path benchmarks; preserve this ownership while sase-zn.9.4/.5 address broader loop/pump/heap responsiveness and live-host evidence.

[2026-09-13T19:46:34Z · sase-100.land] DISCOVERED ISSUE from sase-100 landing, proposed by phase sase-100.3 note #1: commit 70b018b91 (sase-zn.9.2) added pressure_available_bytes and pressure_recovery_available_bytes to managed_tmp_reap summaries but left tests/test_axe_chop_output_contract.py exact counter dictionaries unchanged. Fresh reproduction at HEAD ecfde919c: uv run pytest -q tests/test_axe_chop_output_contract.py::test_managed_tmp_reap_emits_noop_summary tests/test_axe_chop_output_contract.py::test_managed_tmp_reap_emits_action_summary gives 2 deterministic failures, each solely the two extra counters. This is causally owned by the still-active sase-zn.9 pressure-reaping epic; no duplicate task was created.

[2026-09-14T12:22:09Z · sase-zn.9.land--2] Landing verification: all 5 phases confirmed real in code (5554dfb0ce/.1 token revalidation, 70b018b91a/.2 pressure reaping, e5f902ddd6/.3 six bounded caches, 63e16c0fd2/.4 render hitch fixes; .5 deliberately closed by owner waiving multi-day acceptance). Integration review of the ~82 post-epic commits found disk-footprint reporting and Cargo build-dir isolation already using this epic's reaper, and the new section-strip cache following the bounded-LRU pattern. This landing added three integration changes: src/sase/core/managed_tmp_reaper.py rewritten as a thin adapter over sase_core_rs.reap_managed_tmpdir (rust-core-required boundary; resolves parent audit blocker 'shared reaper policy still lives in Python'), tests/test_axe_chop_output_contract.py managed_tmp_reap tests pinned hermetic via _pin_reap_free_space (fixes epic note #2 from sase-100), tests/test_agent_artifact_directory_operation_audit.py stale _remove_if_stale entry removed (deletions moved to Rust). Follow-ups: sase-10t filed (two unbounded ACE TUI caches, phase .3 note #3); sase-lx corroborated by phase .4; all other phase follow-ups verified resolved at HEAD. Combined-tree verification: fmt/lint passed (monitor jwzchstrhcb7); toobig, SASE validation, core-floor advisory probe, committed plans, cost budgets passed and test-cost ran 41535 passed/5 failed (monitor hx7zy0pk3ve8) — all 5 pre-existing/unrelated: 3 nodes broken by master commit 9dbc850062 agent.py split (corroborated sase-10s +1 with scope addition), 1 by c12285ffd4 monitor-start split (corroborated sase-10p +1 with pinpointed fix), 1 new machines-pane parallel-lane flake noted as DISCOVERED ISSUE on owning epic sase-xe.16.11.7. selection-health flake gate names only filed beads sase-10p and sase-10g. symvision blocked repo-wide by pre-existing unrelated sase-10q (corroborated +1 earlier by this landing). No --epic-symbol entries for sase-zn.9.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zn.9.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zn.9.land.md) | [sase-zn.9](sase-zn.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8987960`](https://github.com/sase-org/sase/commit/89879609d10a65c49c5cec2e591458455bfc3be5) | refactor(core): land sase-zn.9 typing-lag epic integration | [sase-zn.9](sase-zn.9.md) | 2026-09-14 09:08:21 EDT |
