# Bead: sase-1om.1 — Stop the TUI roster from dropping monitors and mislabelling holders

[Bead Pages](../README.md) / [sase-1om](README.md) / sase-1om.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.5e.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.5e.linker.w0.md) · **Assignee:** `sase-1om.1` · **Size:** medium
**Created:** 2026-10-26 20:19:44 EDT · **Closed:** 2026-10-26 21:49:14 EDT
**Plan:** [202610/machine\_capacity\_transparency.md](https://github.com/sase-org/sase--plans/blob/main/202610/machine_capacity_transparency.md)

## Description

roster-fixes: give monitor rows their supervisor PID from agent_meta (then the running marker) on every loader path, index holders by agent row instead of workflow-step rows (closing task bead sase-1ol), and carry runner_claim_owner_key through the roster projection, with loader-level regression tests.

## Notes

[2026-10-27T00:44:52Z · sase-1om.1] PROPOSED FOLLOW-UP: Rust agent scans omit generic process_identity from agent_meta and running markers — Python wire models already carry it, but a real scan of metadata containing boot:99 returns None; scanner.rs and wire.rs in sase-core have no generic projection. Consider projecting it and refreshing existing index payloads for non-monitor identity consumers. Monitor-specific supervisor_identity is already projected, so this phase can preserve reused-PID exclusions using that existing field without extra marker reads.

[2026-10-27T00:47:01Z · sase-1om.1] Holder-label defect tracked by sase-1ol is fixed here: both artifact-directory maps now exclude workflow-step children while preserving monitor/session-member rows. Regression verifies agent label, monitor kind, QUEUED status, and queue position despite checkout/diff rows sharing directories. Per phase-worker instruction, only sase-1om.1 will be closed; the land agent can close sase-1ol after integration.

[2026-10-27T01:21:01Z · sase-1om.1] PROPOSED FOLLOW-UP: Integrate the capacity fixture fixes from sase-1oj.4 before epic landing — ToolRun 6f93bab556a13b7f91ad82b08597d97a ran all lint gates and expanded to the full suite after a stale Rust extension refresh: 57,840 passed, 17 skipped, three KNOWN failures (witness 0eefa7f1c9ee0383c9c47942325079fe). All three reproduce identically on a verified clean base at 98cb07ebb8f56aedc9d5f9c044687c8ee342d93a: test_capacity_blocked_waiter_does_not_park_the_queue_behind_it, test_capacity_blocked_head_then_high_budget_launch_uses_real_scan, and test_capacity_only_skips_done_dirs_and_keeps_active_ones. Earlier corroboration is sase-1ok.1 note 1; sase-1oj.4 now reports these fixtures fixed and passing in ToolRun ad01b1a3661b647ee62905f865c53150. This phase does not modify those fixtures.

[2026-10-27T01:23:02Z · sase-1om.1] Implementation complete; remaining work is final verification and closure only, which fits one continuation. Final code recovers monitor PIDs from meta then running markers, marks recovered PIDs unverified, uses the existing monitor.supervisor_identity wire field with shared process_identity_matches (no extra marker reads), preserves runner_claim_owner_key, and skips only workflow-step children in both capacity maps. Final targeted loader/capacity/dedup run: 97 passed. Weighted-capacity screenshot maintenance rerun after the cleanup: clean, 2 unchanged goldens, report b29367a1584d49e2a9a19233a5f7ef3e inspected. just fix and git diff --check pass; epic-symbols reports none. Final just check will run under a verify monitor. Close only sase-1om.1 after reviewing it, accepting the separately documented identical clean-base failures if they recur.

[2026-10-27T01:49:14Z · sase-1om.1--1] Verified roster-fixes against the approved design: monitor supervisor PIDs recover from metadata then running markers across all loaders, process identity excludes reused PIDs, runner_claim_owner_key survives enrichment/dedup/projection, and workflow-step rows cannot replace holder or queue labels. Final ToolRun 91b805cb164fd954e29096d4d8919ef5: all lint/validation stages passed; 11,709 tests passed, with only two KNOWN capacity-scan fixture failures and verdict no_new_failures (exit 1). Both failures match the identical clean-base evidence and sase-1oj.4 integration follow-up recorded in note 3. Prior final targeted loader/capacity/dedup run passed 97 tests; weighted-capacity PNG maintenance was clean with 2 unchanged goldens (report b29367a1584d49e2a9a19233a5f7ef3e inspected). Final git diff --check passed and epic-symbols reported no entries. Only this phase is closed; sase-1ol and the parent epic remain for the land agent.

## Dependencies

- **Blocks:** [sase-1om.6](sase-1om.6.md) ✓ · ⧖ 2026-10-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1om.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1om.1.md) | [sase-1om.1](sase-1om.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cef4bb1`](https://github.com/sase-org/sase/commit/cef4bb119942ee627f18ad82e153124620dbbdd0) | fix(tui): preserve monitor capacity in roster projections | [sase-1om.1](sase-1om.1.md) | 2026-10-26 21:50:26 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1om.1--1][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1om.6--2][2] | Compare the clean-base test reproduction and known failures with this phase's check result | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1om.1.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1om.6.md

<!-- sase:referenced-by:end -->
