# Bead: sase-fp.8.2 — Change-scoped false-negative correlation

[Bead Pages](../README.md) / [sase-fp.8](sase-fp.8.md) / sase-fp.8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-fp.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fp.land/README.md) · **Assignee:** `sase-fp.8.2` · **Size:** medium
**Created:** 2026-08-06 01:41:48 EDT · **Closed:** 2026-08-06 02:10:22 EDT
**Plan:** [202608/test\_selection\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/test_selection_landing.md)

## Description

correlate: record the workspace and change-set identity that the false-negative definition requires on full-run health records, restrict find_false_negatives to pairs that describe the same change, and re-read the metric.

## Notes

[2026-08-06T06:09:35Z · sase-fp.8.2] PROPOSED FOLLOW-UP: full-run failure records capture xdist worker IDs as node IDs — the store at HEAD holds a "gw22" entry (a worker-crash CollectReport) that the correlator treated as a test file and reported as a false negative; FullRunFailureRecorder should drop node IDs that do not resolve to a repo test path.

[2026-08-06T06:10:22Z · sase-fp.8.2] correlate: full-run and scoped health records now carry the identity the false-negative definition requires, and find_false_negatives only pairs records that plausibly describe the same change.

WHAT CHANGED
- HEALTH_SCHEMA 1 -> 2. Selection records carry a 'workspace' envelope field; full-run records carry 'workspace' and 'changed_files'. Workspace identity is the resolved repo root (workspace_identity()), not a digest: the store is host-local and already per-project, so the path is as stable as a hash while staying legible — .../sase_3 vs .../sase_11 is exactly the distinction the metric turns on.
- tools/run_pytest computes the full lane's change set with the selector's own compute_change_set() against SelectionOptions.from_environment().base_ref, in the parent process before execv, and passes it plus the workspace through RECORD_ENV; the plugin writes both. Git trouble yields explicit nulls, making the record uncorrelatable rather than wrongly correlated.
- find_false_negatives now requires: same workspace, scoped HEAD an ancestor of the full run's HEAD, and the full run's change set a superset of or equal to the scoped run's — on top of the existing not-escalated, not-selected, and visual-path exclusions.
- Records with no identity (everything pre-schema-2) are skipped and counted by count_pre_schema_records(); the report says how many, so a zero is never mistaken for a clean sample.
- The matching rule is stated in the module docstring and printed in every 'just selection-health' report, zero count or not.
- Per-nodeid output now reports 'distinct change sets: N' and, when N > 1, 'matched across unrelated changes; suspect a flake before a miss'. No flake detection was attempted, per the plan.
- health_payload gained pre_schema_selections/pre_schema_full_runs and per-finding workspace + selection_changed_files.

CORRECTED READING (be honest about the sample)
Before: 10 false negatives across 37 scoped-run/failure matches — every one an artifact of cross-workspace matching (the plan documented 9/32 at d66101e8f; the store grew since).
After: 0 false negatives, and 28 of the store's 29 records (9 scoped, 19 of 20 full-lane) predate schema 2 and are excluded from correlation. The only schema-2 record is the one this phase's own check-full wrote. The epic's exit criterion — zero false negatives across at least 30 varied changes — is NOT met and cannot be met yet; that sample does not exist. The corrected metric is what makes the question answerable over the coming weeks, and it no longer argues for raising SASE_TEST_SELECTION_DEPTH on the strength of noise.

VERIFIED
- Unit coverage over synthetic records, all new: same-workspace/same-change match; cross-workspace non-match; disjoint-change non-match; superset-change match; legacy records skipped and counted; escalated manifests still skipped; visual paths still skipped; workspace_identity resolves symlinks; the report states the rule, the pre-schema count, and the unrelated-change flake signature; the plugin round-trips workspace and changed_files to disk; the runner request carries both and the scoped record carries the workspace.
- End-to-end on the real store: the full-lane record this phase wrote is schema 2 with workspace=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_11 and the six-file change set, and the report counts it as the one non-pre-schema full run.
- just check-full: every lint gate green (including _lint-symvision and the contract-manifest sync guard); 25,820 passed, 7 skipped, 1 failed — tests/test_bead/test_cli_work_contention_regressions.py::test_concurrent_bead_mutations_wait_past_the_old_lock_timeout, the load-sensitive flake named in the plan's follow-up 6, confirmed passing standalone (5.6s) and untouched by this change.
- Recorded one PROPOSED FOLLOW-UP: xdist worker IDs ('gw22') land in full-run failure records as node IDs and were being reported as false negatives.

NOT COMMITTED: the working tree carries the change; no commit was requested.

[2026-08-06T06:11:13Z · sase-fp.8.2] correlate phase verified: unit coverage for all seven correlation cases, workspace identity, report rule/pre-schema/flake-signature lines, plugin+runner handoffs; just check-full lint gates green, 25820 passed with one known load-sensitive flake passing standalone.

## Dependencies

- **Blocks:** [sase-fp.8.3](sase-fp.8.3.md) ◐ · ⧖ 2026-08-06

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fp.8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fp.8.2/README.md) | [sase-fp.8.2](sase-fp.8.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e7917a2`](https://github.com/sase-org/sase/commit/e7917a2682e81c2119509e75bbdf19e7c4da0796) | fix(tests): restrict selection-health false-negative correlation to matching changes | [sase-fp.8.2](sase-fp.8.2.md) | 2026-08-06 02:12:42 EDT |
