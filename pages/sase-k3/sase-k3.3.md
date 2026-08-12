# Bead: sase-k3.3 — Deferred persisted diff-badge classification

[Bead Pages](../README.md) / [sase-k3](README.md) / sase-k3.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.yo](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.yo/README.md) · **Assignee:** `sase-k3.3` · **Size:** medium
**Created:** 2026-08-12 11:37:29 EDT · **Closed:** 2026-08-12 14:10:21 EDT
**Plan:** [202608/ace\_startup\_critical\_path.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_startup_critical_path.md)

## Description

badges: stop classifying persisted diff badges inside the loader's status-override pass and compute them for visible rows only in a coalesced background pass modeled on the existing bead-warmup and live-hint mixins, with carry-over across reloads so badges do not flicker on refresh.

## Notes

[2026-08-12T18:10:21Z · sase-k3.3] Implemented deferred, coalesced background classification of persisted diff badges (diff_has_real_edits + linked_file_change_hint), modeled on AgentBeadWarmupMixin: new AgentDiffBadgeMixin (_loading_diff_badges.py) with the standard scheduled/running/pending/source coalescing flags (initialized in _state_init.py), spawn_pump_free_task + nav-gate deferral + asyncio.to_thread for the disk reads, results keyed by agent.identity and applied via _try_patch_agent_row. Both loader call sites (_agent_loader_normalization.py's normalize_loaded_agents and _loading_compute_merge.py's post-merge apply_status_overrides) now pass classify_diff_badges=False; candidates are scoped to visible rows only (self._agents) and deduped via a shared DiffBadgeResultCache. Added carry_over_diff_badges (same shape as carry_over_live_hints) wired into _loading_apply.py so refreshes don't flicker the pencil column. Confirmed via the real-terminal trace below that the linked-commit-diff branch is not where the byte volume concentrates (dedup collapses it before scheduling either way, per the DiffBadgeResultCache shared across the whole batch). Verified: just check green (fmt/ruff/mypy/pyscripts/test-waits/changelog/patch-terminology/symvision/toobig/SASE-validation/committed-plans, plus the full escalated test suite, 29194+ passed). Along the way fixed 4 test harnesses (tests/_agents_tab_query_helpers.py FakeAgentApp, tests/_agent_loader_self_heal_helpers.py FakeLoadingApp, tests/ace/tui/test_apply_path_index_maintenance_offthread.py _ApplyHarness, tests/ace/tui/test_post_launch_jk_lag.py _FakeApplyApp/_FakeRefreshApp) that extend the apply pipeline directly and were missing the new _diff_badge_scan_* stub state, which just check's full run caught as 32 failures on the first pass. Ported tests/test_agent_loader_status_override_tale.py (:502/:546) to drive the deferred pass instead of asserting loader-time classification; confirmed tests/test_agent_loader_live_file_change_hint.py needed no change since it exercises _apply_status_overrides directly with an explicit classify_diff_badges=True, not the loader default. Added tests/ace/tui/test_agents_diff_badge_deferred.py covering dedup (N refs over M paths -> M reads), coalescing under a refresh burst, identity re-matching when the list rebuilds mid-flight, and carry-over across a reload. Real-terminal capture: launched sase ace -T against real project data (32 agent rows, 535 index rows) and quit after load; ~/.sase/logs/tui_startup.jsonl recorded agents_ready_seconds=4.49s/visible_ready_seconds=3.49s (loader path, no longer blocked on diff reads), and ~/.sase/perf/tui_trace.jsonl recorded a genuine agents.diff_badge_classification span: candidates=11, duration_ms=542.5, source=apply -- confirming the deferred background pass fires after apply, is scoped to visible rows (11, not the full 1,178-reference/492-path set the inline classifier used to read), and settles the badges without blocking startup. Did not have an isolated pre-change checkout in this session to produce a strict controlled 3x-before/3x-after diff (this machine has several sibling-epic agents running concurrently against the same shared ~/.sase telemetry log), so the loader-side savings are reported per the plan's own static analysis (1,178 calls/492 paths/19.8MB/~0.40s removed from the critical path) rather than a fresh A/B wall-clock pair; the badge-settle time above is a genuine new measurement, reported separately from agents-load time as requested.

## Dependencies

- **Depends on:** [sase-k3.1](sase-k3.1.md) ✓ · ⧖ 2026-08-12
- **Blocks:** [sase-k3.6](sase-k3.6.md) ◐ · ⧖ 2026-08-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-k3.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-k3.3/README.md) | [sase-k3.3](sase-k3.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`14fcbc2`](https://github.com/sase-org/sase/commit/14fcbc21a104c2252270ea0be97324231a221b50) | perf(ace): defer persisted diff-badge classification off the loader (sase-k3.3) | [sase-k3.3](sase-k3.3.md) | 2026-08-12 14:12:11 EDT |
