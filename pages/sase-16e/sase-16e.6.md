# Bead: sase-16e.6 — Truthful setup-failure reporting

[Bead Pages](../README.md) / [sase-16e](README.md) / sase-16e.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pc](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pc.md) · **Assignee:** `sase-16e.6` · **Size:** small
**Created:** 2026-09-22 12:13:34 EDT · **Closed:** 2026-09-22 13:02:22 EDT
**Plan:** [202609/self\_healing\_workspace\_prep.md](https://github.com/sase-org/sase--plans/blob/main/202609/self_healing_workspace_prep.md)

## Description

visibility: make a recorded runner error beat the synthesized "Runner exited without recording an error" fallback in the TUI, and make runner stdout line-buffered so the output file interleaves stdout/stderr correctly.

## Notes

[2026-09-22T17:01:39Z · sase-16e.6] PROPOSED FOLLOW-UP: 11 just check scoped tests fail identically on clean tree (commit_bead_hooks, cli_at_path_values, usage_config x4, test_shards, epic_panel_arrival_frames, session_proc_reporter) — triage as environment/flake task

[2026-09-22T17:02:22Z · sase-16e.6] Recorded done.json errors beat the synthetic runner-failure fallback via error_is_synthetic flag (dedup_running_vs_workflow); runner stdout line-buffered at main() entry with stdio flush before AGENT_RUN_COMPLETE marker. Verified: 19/19 tests pass in test_agent_loader_dedup_merge, test_workflow_failure_fallback, test_runner_output_interleaving (incl. subprocess interleave+marker-last test with failing negative control); all lint gates pass; no sase-core agent-scan mirror exists (merge is Python-only); 11 unrelated scoped failures reproduce identically on clean tree.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16e.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16e.6/README.md) | [sase-16e.6](sase-16e.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1a96a22`](https://github.com/sase-org/sase/commit/1a96a22f171c845da339870d6cf054828dbf655f) | fix(ace-runner): recorded errors beat synthetic fallback; truthful runner output ordering | [sase-16e.6](sase-16e.6.md) | 2026-09-22 13:05:22 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16e.6][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16e.6/README.md

<!-- sase:referenced-by:end -->
