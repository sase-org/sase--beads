# Bead: sase-tt.6 — Defer plan metadata reads past the inventory slice

[Bead Pages](../README.md) / [sase-tt](README.md) / sase-tt.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0do](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0do.md) · **Assignee:** `sase-tt.6` · **Size:** medium
**Created:** 2026-08-25 14:59:15 EDT · **Closed:** 2026-08-25 16:31:44 EDT
**Plan:** [202608/artifacts\_query\_performance.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_query_performance.md)

## Description

plans: stop reading and YAML-parsing every archived plan file to produce fifty rows, and stop computing the rejected section for callers that only asked for proposed plans.

## Notes

[2026-08-25T20:31:16Z · sase-tt.6] PROPOSED FOLLOW-UP: `just check`'s SASE validation gate (`sase validate` -> `init memory --check`) fails on a clean master checkout, independent of this phase — `sase/artifact_relations.json`, `AGENTS.md`, `CLAUDE.md`, `GEMINI.md`, `QWEN.md`, `OPENCODE.md` are stale relative to `sase memory init` output. The same root cause also fails `tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift`, `test_current_structural_view_matches_checked_in_snapshot`, and `tests/main/test_init_memory_committed_drift.py::test_repo_project_memory_notes_match_generator_output` on clean master (confirmed via `git stash` + rerun, no local changes). Someone likely landed a change affecting generated memory/completion output without running `sase memory init` / regenerating the committed snapshot.

[2026-08-25T20:31:44Z · sase-tt.6] Implemented the plans phase: (1) plan_inventory.py skips collect_rejected_plans entirely when statuses excludes 'rejected' (e.g. the Artifacts pane's limit:50 statuses=(proposed,) call), keeping total_archived_proposals from the cheap archived_plan_paths() count; (2) collect_rejected_plans and collect_approved_plans in plan_inventory_collectors.py now sort/dedupe candidates by mtime/timestamp first and call plan_metadata_for_path only for the rows actually selected (tier-filtered calls keep the eager read, since tier gates inclusion); (3) plan_inventory_paths.plan_metadata_for_path is now memoized behind a bounded (mtime_ns, size)-signature-keyed cache mirroring plan_tiers._PLAN_TIER_CACHE. Verified: full plan-inventory/plan-tiers/plan-list test files pass (63 tests, 3 new: two isolating that metadata reads are bounded to the selected slice, one confirming collect_rejected_plans is never invoked when rejected isn't requested). tests/perf/bench_artifacts_first_paint.py's Plan pane first paint dropped from the documented ~2,536ms baseline to ~373ms p50 (640ms p95), meeting the epic's <=400ms p50 target. just fmt/lint gates (ruff, mypy, keep-sorted, feature-flags, pyscripts, test-waits, changelog, patch/stitch terminology, symvision, toobig) all pass. just check's SASE-validation step and just test-scoped's 3 failures (completion snapshot + init-memory-committed-drift) were confirmed via git-stash rerun to be pre-existing on clean master, unrelated to this diff; noted as a PROPOSED FOLLOW-UP on this bead. No --epic-symbol entries were present (sase bead epic-symbols sase-tt.6).

## Dependencies

- **Depends on:** [sase-tt.1](sase-tt.1.md) ✓ · ⧖ 2026-08-25
- **Blocks:** [sase-tt.8](sase-tt.8.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-tt.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-tt.6/README.md) | [sase-tt.6](sase-tt.6.md) | 0 |
