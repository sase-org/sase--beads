# Bead: sase-zu.8.5 — Verify the pinned cohort and complete measured acceptance

[Bead Pages](../README.md) / [sase-zu.8](sase-zu.8.md) / sase-zu.8.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zu.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zu.land.md) · **Assignee:** `sase-zu.8.5` · **Size:** medium
**Created:** 2026-09-13 10:21:18 EDT · **Closed:** 2026-09-13 17:06:12 EDT
**Plan:** [202609/agent\_query\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_query_landing_repairs.md)

## Description

acceptance: verify the selected Rust revision and supported install, prove production-path parity and performance on synthetic and real archives, publish evidence, and finish the three flag retirements.

## Notes

[2026-09-13T19:33:33Z · sase-zu.8.5--1] PROPOSED FOLLOW-UP: ACE bounded Agents loads source-scan for 6.7-7.4 s when the process-local artifact-index RLock is held past its 50 ms read timeout — 62ad9b657c query_agent_artifact_index_bounded falls back to scan_agent_artifacts on lock busy; the athena sase-zu.8.5 session logged 3 such auto_refresh/dismissed_index_sync fallbacks before settling; retry or defer to the index instead of a full source scan.

[2026-09-13T19:33:57Z · sase-zu.8.5--1] PROPOSED FOLLOW-UP: single non-selective full-history load is ~1x source scan on the warm 13k fixture (0.96x) — shared per-row Python work dominates (dict-to-wire ~1.3 s, Agent decode ~2.0 s, agents-live field entries ~2.9 s) and revalidate adds ~660 ms Rust (source reconcile plus 12,938 marker signatures); consider retaining decoded rows keyed by marker signature, lazy decode, or skipping hidden-row marker repair already covered by the reconcile pass.

[2026-09-13T19:34:21Z · sase-zu.8.5--1] PROPOSED FOLLOW-UP: tier1_index_revalidate on athena checks ~6,800 hidden-row marker signatures (~1.1 s every revalidate) because repair_stale_rows_for_query re-signs every hidden row; bound or incrementalize hidden-row repair in sase-core without losing unhide detection.

[2026-09-13T19:34:45Z · sase-zu.8.5--1] PROPOSED FOLLOW-UP: source-scan fallback loads show members of dismissed families that index loads hide — the Rust index lineage dismissal (sase-core 34b3229) hides descendants of dismissed family roots but Python compute_apply_loaded_agents does not; athena has 13 such --code/--mon rows; make the fallback use the Rust dismissal decision.

[2026-09-13T19:35:51Z · sase-zu.8.5--1] PROPOSED FOLLOW-UP: published dependency floor lags the pinned cohort — pyproject allows sase-core-rs>=0.34.23 but schema-30 index / scan-wire-9 support exists only at pin 23f19f0 (after the v0.34.24 release commit 782dc74); a sase release must wait for a sase-core release and a tools/ratchet_core_window floor bump, otherwise a PyPI install gets a binding without the machine-parity/completeness fixes.

[2026-09-13T21:05:47Z · sase-zu.8.5--3] PROPOSED FOLLOW-UP: cut a sase-core release containing 23f19f0 and raise the sase-core-rs floor before publishing — just check core-floor-probe reports blocked_unpublished (0.34.23 lacks artifact_ref_link_location_wire_schema_version, artifact_ref_split_link_location from 17947a0 and continuation_decide_resume_adoption, continuation_plan_retention from 23f19f0; no release tag contains them yet). Non-blocking for local gates (exit 0).

[2026-09-13T21:06:12Z · sase-zu.8.5--3] Acceptance verified. Pin 23f19f0 install/binding: just install exit 0; binding reports index schema 30, scan wire 9, exposes continuation_decide_resume_adoption (installer downgrade proposal from sase-zu.4 not reproduced). Production oracle zero-diff; oracle + tests/perf 80 passed/1 skipped. Synthetic 13k: bounded first paint 101 ms p50 (88x); production full history 9281 ms p50 vs source 8933 (0.96x, attributed to shared per-row Python decode/filter plus ~660 ms revalidate); 0 missing/0 extra; periodic revalidate 136 ms/339 marker checks; 10-refresh session 10.6x with one full-history read. Athena real archive: full history 2989 vs 10866 ms (3.64x), bounded 10.8x, session 12.6x; 13 missing explained by pre-epic Rust lineage dismissal (34b3229), 1 extra from an agent created mid-run. Live ACE session: agents_ready_seconds 6.457, exactly one input_quiet_tier2_reconcile (7154 ms) plus one explicit manual_full_history (4066 ms), 13 cached refreshes and 20 exact deltas, no repeated full-history loads; 3 early lock-busy source-scan fallbacks recorded as follow-up. Evidence published in docs/perf_runbook.md 'Measured acceptance (sase-zu.8.5)'. Flag beads sase-zx/sase-101/sase-107 closed; sase-109 memory task remains open as the tui_perf disposition. just check-full: all lint gates green, 2 of 41385 tests failed, both phase-8.4 regressions from d698f92e05 (stale _SearchLoadApp._schedule_agents_async_refresh stub; dropped _adds_structural_placement suffix-shadow guard in merge_incomplete_load_after_complete_history) — both fixed here (guard restored, exact artifact deltas still always replace), verified by focused suites (386 passed/1 skipped) and a follow-up just check exit 0. epic-symbols empty. Core-floor probe blocked_unpublished noted as follow-up.

## Dependencies

- **Depends on:** [sase-zu.8.4](sase-zu.8.4.md) ✓ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zu.8.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zu.8.5.md) | [sase-zu.8.5](sase-zu.8.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ef254fd`](https://github.com/sase-org/sase/commit/ef254fd6dcb4bfbf3d14243579d2f96ea6a8708c) | test(perf): complete agent load tiering measured acceptance | [sase-zu.8.5](sase-zu.8.5.md) | 2026-09-13 17:21:40 EDT |
