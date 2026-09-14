# Bead: sase-zn.9.3 — Attribute residual ACE retention and guard the whole application

[Bead Pages](../README.md) / [sase-zn.9](sase-zn.9.md) / sase-zn.9.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zn.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zn.land.md) · **Assignee:** `sase-zn.9.3` · **Size:** medium
**Created:** 2026-09-12 17:29:04 EDT · **Closed:** 2026-09-13 11:20:39 EDT
**Plan:** [202609/finish\_ace\_typing\_lag.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_ace_typing_lag.md)

## Description

heap_attribution: use the shipped sampler on a representative long-lived ACE session, fix measured retention sites, and add a bounded repeated-refresh regression.

## Notes

[2026-09-13T15:09:56Z · sase-zn.9.3] PROPOSED FOLLOW-UP: just check fails the whole-repo symvision gate on an unrelated pre-existing issue -- apply_resume_adoption in src/sase/monitor/resume.py (added by unrelated commit 897147eac2, not by this phase) is flagged as an unused public function/class. Needs private-rename or a real caller.

[2026-09-13T15:10:28Z · sase-zn.9.3] PROPOSED FOLLOW-UP: this workspace's installed sase_core_rs extension is stale relative to recent commits -- test_check_sase_core_rs_bindings_tool.py::test_dev_extension_exposes_every_collected_name fails because continuation_decide_resume_adoption (added by unrelated commit 897147eac2) is missing from the built module. The same staleness likely explains a cluster of unrelated just test-scoped failures in tests/monitor/test_monitor_resume.py, tests/monitor/test_continuation_delivery.py, tests/test_xprompt_directive_completion_parity.py, tests/test_queue_directive.py, and tests/main/test_completion_candidates_contract.py (22 failed / 41253 passed on the full scoped run for this phase, none touching sase-zn.9.3's changed files). Needs a rebuilt/reinstalled sase_core_rs wheel in affected workspaces.

[2026-09-13T15:10:58Z · sase-zn.9.3] PROPOSED FOLLOW-UP: two more module-level ACE TUI caches grow unbounded but were left unfixed in this phase because a correct fix needs more than a size cap. src/sase/ace/tui/tools/cache.py::_tools_cache is keyed by agent identity and rewritten repeatedly for a still-running agent (the same hot-rewrite hazard fixed here via LRU in _linked_deltas.py and axe_log_renderer.py); invalidate_cached_tool_calls() only mutates an existing entry, never pops one. src/sase/ace/tui/actions/agents/_snapshot_cache.py::_GLOBAL_CACHE already has invalidate()/invalidate_dismissed_bundles() methods but grep confirms no production caller ever invokes them -- dead eviction API sitting on a monotonically growing dict. Both grow far slower than the per-second Tier-1 sites fixed here (bounded by distinct-agent count, not elapsed time), which is why they were triaged out of this phase's scope.

[2026-09-13T15:20:39Z · sase-zn.9.3] Attributed and fixed residual ACE retention. Live sase_zn_9_3_heap_evidence run using the shipped TUIHeapSampler + live_agent_file_change_hint (10 synthetic active agents, 90 real-time ticks/phase) showed the pre-fix code growing _diff_cache linearly with no bound (900 entries / 3.7MB traced at tick 90, still climbing) versus the same workload plateauing exactly at the 128-entry cap (139520 bytes, flat from tick 15 through 90) once the fix was restored mid-run. Root cause: _diff_cache's key embeds a per-second TTL bucket that is never reused, so every active-agent probe added a permanent entry; the deferred live-hint scan runs this on every Agents-tab refresh.

Fixed 6 confirmed-unbounded module-level caches with bounded eviction: _diff_cache (_diff.py), _linked_diff_text_cache/_linked_delta_cache/_selected_agent_linked_delta_cache+_selected_agent_cache_monotonic (_linked_deltas.py), _render_cache (axe_log_renderer.py), _diff_badge_cache (_diff_badge.py), artifact_links._CACHE, and link_index._INDEX_CACHE. Used plain FIFO where a key is written once (TTL- or content-signature-keyed); used real LRU (OrderedDict.move_to_end) where a live entity keeps rewriting its own slot (_selected_agent_linked_delta_cache, _render_cache), since FIFO there would evict the busiest live agent/row first -- verified with a dedicated regression per cache proving the hot entry survives while cold ones cycle out.

Added deterministic regression tests (test_diff_cache.py, test_linked_deltas.py, test_axe_log_renderer.py, test_diff_badge.py, new test_relation_cache_bounds.py) driving thousands of simulated refresh ticks and asserting each cache stays at/under its explicit cap instead of growing unboundedly.

Verified: pytest on all touched test files (150 passed) plus full 
┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.0.2, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_19
configfile: pyproject.toml
plugins: cov-7.0.0, asyncio-1.3.0, hypothesis-6.151.9, xdist-3.8.0, inline-snapshot-0.32.5, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [6254 items]

........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  4%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  8%]
........................................................................ [  9%]
........................................................................ [ 10%]
........................................................................ [ 11%]
........................................................................ [ 12%]
........................................................................ [ 13%]
........................................................................ [ 14%]
........................................................................ [ 16%]
........................................................................ [ 17%]
........................................................................ [ 18%]
........................................................................ [ 19%]
........................................................................ [ 20%]
........................................................................ [ 21%]
........................................................................ [ 23%]
........................................................................ [ 24%]
........................................................................ [ 25%]
........................................................................ [ 26%]
........................................................................ [ 27%]
........................................................................ [ 28%]
........................................................................ [ 29%]
........................................................................ [ 31%]
........................................................................ [ 32%]
........................................................................ [ 33%]
........................................................................ [ 34%]
........................................................................ [ 35%]
........................................................................ [ 36%]
........................................................................ [ 37%]
........................................................................ [ 39%]
........................................................................ [ 40%]
........................................................................ [ 41%]
........................................................................ [ 42%]
........................................................................ [ 43%]
........................................................................ [ 44%]
........................................................................ [ 46%]
........................................................................ [ 47%]
........................................................................ [ 48%]
........................................................................ [ 49%]
........................................................................ [ 50%]
...........................................F............................ [ 51%]
........................................................................ [ 52%]
........................................................................ [ 54%]
........................................................................ [ 55%]
........................................................................ [ 56%]
........................................................................ [ 57%]
........................................................................ [ 58%]
........................................................................ [ 59%]
........................................................................ [ 61%]
........................................................................ [ 62%]
........................................................................ [ 63%]
........................................................................ [ 64%]
........................................................................ [ 65%]
........................................................................ [ 66%]
........................................................................ [ 67%]
........................................................................ [ 69%]
........................................................................ [ 70%]
......................................................s................. [ 71%]
........................................................................ [ 72%]
........................................................................ [ 73%]
........................................................................ [ 74%]
........................................................................ [ 75%]
.......................................................

… and 11522 more characters

## Dependencies

- **Depends on:** [sase-zn.9.1](sase-zn.9.1.md) ✓ · ⧖ 2026-09-12
- **Depends on:** [sase-zn.9.2](sase-zn.9.2.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zn.9.5](sase-zn.9.5.md) ✓ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zn.9.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zn.9.3/README.md) | [sase-zn.9.3](sase-zn.9.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e5f902d`](https://github.com/sase-org/sase/commit/e5f902ddd66c2c0c63e447f9365d7c99b0deef02) | fix(ace-tui): bound six unbounded module-level caches driving residual heap growth | [sase-zn.9.3](sase-zn.9.3.md) | 2026-09-13 11:32:39 EDT |
