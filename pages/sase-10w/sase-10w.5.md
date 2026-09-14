# Bead: sase-10w.5 — Observe green CI and feed the selector a fresh baseline

[Bead Pages](../README.md) / [sase-10w](README.md) / sase-10w.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0kh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0kh.md) · **Assignee:** `sase-10w.5` · **Size:** medium
**Created:** 2026-09-14 09:06:49 EDT
**Plan:** [202609/green\_ci\_fast\_lane\_v0\_17\_2.md](https://github.com/sase-org/sase--plans/blob/main/202609/green_ci_fast_lane_v0_17_2.md)

## Description

green-ci-and-baseline: watch Master Gate go green on the tip, dispatch and watch a fully green Full CI whose coverage-contexts job uploads a .coverage baseline, then install that baseline locally and verify the scoped lane consults it instead of depth-boosting.

## Notes

[2026-09-14T15:40:41Z · sase-10w.5] EVIDENCE: Master Gate run 34861266462 on cc91c0aa failed because the pinned CI core wheel lacked seven required bindings; lint failed in tools/check_sase_core_rs_bindings and shards hit missing proc_runtime_retention_wire_schema_version. Local repair bumps sase-core-revision.txt from a35b18220fb3 to afe7b70dbede, whose core checkout exports all seven names. Verified locally: just install; .venv/bin/python tools/check_sase_core_rs_bindings => all 598 bindings exposed; direct seven-symbol probe => missing=[]; just check => green, with scoped lane escalated to full suite because rules contract-set-only/core-identity-changed, so contexts baseline was not consulted on this core-pin diff. Current selection-health: 2343 scoped runs, 1551 escalated (66.2%), median 121.8s, p90 648.8s, context-baseline-stale/no-baseline-depth-boost 832 each, serial-budget-exceeded 436. Remaining before close: land the pin fix, watch Master Gate green, dispatch/watch Full CI including coverage-contexts upload, refresh baseline, and prove a non-core small diff consults the fresh baseline.

[2026-09-14T15:40:43Z · sase-10w.5] PROPOSED FOLLOW-UP: publish and ratchet the sase-core-rs floor before v0.17.2 release - just check core-floor-probe reports published sase-core-rs==0.34.26 missing seven required bindings (agent_artifact_run_retention*, proc_runtime_retention*, argument_colon_to_parentheses_edit, git_object_sharing*) and no containing sase-core release tag exists yet.

## Dependencies

- **Depends on:** [sase-10w.1](sase-10w.1.md) ✓ · ⧖ 2026-09-14
- **Depends on:** [sase-10w.2](sase-10w.2.md) ✓ · ⧖ 2026-09-14
- **Depends on:** [sase-10w.3](sase-10w.3.md) ✓ · ⧖ 2026-09-14
- **Depends on:** [sase-10w.4](sase-10w.4.md) ✓ · ⧖ 2026-09-14
- **Blocks:** [sase-10w.6](sase-10w.6.md) ◐ · ⧖ 2026-09-14

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-10w.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-10w.5/README.md) | [sase-10w.5](sase-10w.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9ff2662`](https://github.com/sase-org/sase/commit/9ff2662c0cb7ea116faa07d58515e26985c52e15) | fix(ci): bump pinned sase-core revision | [sase-10w.5](sase-10w.5.md) | 2026-09-14 11:42:24 EDT |
