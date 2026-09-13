# Bead: sase-zu.8 — Finish indexed agent-history correctness, reuse and measured acceptance

[Bead Pages](../README.md) / [sase-zu](README.md) / sase-zu.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zu.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zu.land.md) · **Assignee:** `sase-zu.8.land`
**Created:** 2026-09-13 10:21:12 EDT · **Closed:** 2026-09-13 18:02:56 EDT
**Plan:** [202609/agent\_query\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_query_landing_repairs.md)

## Description

Repair the confirmed row-loss and freshness gaps, preserve later queue and Refresh panel changes, and prove the remaining sase-zu acceptance criteria.

## Notes

[2026-09-13T20:19:36Z · 55--code] DISCOVERED ISSUE: During swap_agents_retry_refresh implementation (2026-09-13), the full just-check lane failed tests/test_agent_loader_incomplete_history_dedup.py::test_incomplete_load_after_complete_history_keeps_non_workflow_suffix_guard: expected cached RUNNING cl_name 'active', got 'unknown'. Isolated rerun still fails. The keymap change does not touch the agent loader. Routed here because this epic owns indexed agent-history correctness. No new task.

[2026-09-13T22:02:56Z · sase-zu.8.land] Landing verified by sase-zu.8.land on master ef254fd6dc (the epic's own acceptance commit at HEAD). (1) VERIFY: all five phases closed and their work confirmed in the tree — db6fd25182 routed the parity oracle through load_tiered_agents with post-index-build mutation helpers; 5beda061fc made cached full-history completeness depend on the Rust source-reconcile watermark (snapshot.index_completeness adopted in query_artifact_index_for_loader) and bounded Tier 1 revalidate; 1cd445ae4f stores both live machine values (schema 30) with relative expansion so machine candidates never under-select; d698f92e05 added query-keyed stale-discard, exact active-query deltas, delta-loss completion invalidation, and the completion-time Refresh freshness stamp; ef254fd6dc verified the pin cohort and published measured acceptance in docs/perf_runbook.md (synthetic 13k: bounded first paint 88x, session 10.6x; athena: full history 3.64x, session 12.6x; zero settled missing/extra modulo explained pre-epic dismissal rows). Pin coherence proven: 23f19f0 is the direct parent of the current pin 7f43a996. Flag beads sase-zx/sase-101/sase-107 closed; sase-109 stays open as the tui_perf memory disposition. Epic DISCOVERED ISSUE note #1 (test_incomplete_load_after_complete_history_keeps_non_workflow_suffix_guard) verified fixed by ef254fd6dc's restored suffix-shadow guard — file passes 5/5 at HEAD. sase-zu.8.1's two follow-ups verified resolved on the current tree: apply_resume_adoption is now private and used in-file, and the bindings tool test passes 10/10 with continuation_decide_resume_adoption exposed. (2) INTEGRATE: 13 non-epic commits interleaved with the epic; the epic's final commit sits above all of them and 8.5's just check-full ran on that merged tree (2 failures, both its own 8.4 regressions, fixed in ef254fd6dc, follow-up just check exit 0). docs/ace.md Refresh prose (ecfde919c5) already matches 8.4's completion-time stamping; the r/R swap (5be4f6ae32) was exercised by 8.5's live acceptance session. No integration changes needed. (3) FOLLOW-UP DISPOSITIONS from sase-zu.8.5: #1 (lock-busy source-scan fallback) and #4 (fallback dismissal parity) are caused by active epic sase-zn (commits 62ad9b657c/zn.5, sase-core 34b3229/zn.2) — recorded as DISCOVERED ISSUE notes on sase-zn, no tasks. #2 (warm full-history ~1x source scan, shared per-row decode) — new task sase-10e (large). #3 (hidden-row revalidate re-sign cost) — semantic duplicate of sase-vc, corroborated with +1. #5+#6 (published floor lags pin; release needed) — new task sase-10d (small) plus a DISCOVERED ISSUE note on parent sase-zu since the epic's lineage caused it; release-gated per sase-wg precedent. Related links for sase-10d/sase-10e recorded as notes because the hidden plans clone holds another agent's untracked link event. epic-symbols: none.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zu.8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zu.8.land/README.md) | [sase-zu.8](sase-zu.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@90387a9`](https://github.com/sase-org/sase--plans/commit/90387a9ea45011ebcb32736f66e635152236b868) | docs(plans): add agent query landing repairs plan (sase-zu.8 land) | [sase-zu.8](sase-zu.8.md) | 2026-09-13 18:17:46 EDT |
