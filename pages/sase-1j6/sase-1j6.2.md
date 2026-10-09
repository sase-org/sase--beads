# Bead: sase-1j6.2 — Runner boot identity, lifecycle breadcrumbs, and failure facts

[Bead Pages](../README.md) / [sase-1j6](README.md) / sase-1j6.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.47.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.47.linker.w0.md) · **Assignee:** `sase-1j6.2` · **Size:** medium
**Created:** 2026-10-09 15:02:05 EDT · **Closed:** 2026-10-09 15:55:11 EDT
**Plan:** [202610/update\_skew\_agent\_auto\_restart.md](https://github.com/sase-org/sase--plans/blob/main/202610/update_skew_agent_auto_restart.md)

## Description

failure-facts: persist the runner's boot code identity and lifecycle-phase breadcrumbs in agent_meta, and record stdlib-only structured failure facts plus a skew-suspect prefilter in done.json at every runner failure writer.

## Notes

[2026-10-09T19:54:52Z · sase-1j6.2] PROPOSED FOLLOW-UP: Add the decisions-web record for update-skew restarts (at most once per lineage, pre-provider only); skipped per epic auto-decision decision_record=no

[2026-10-09T19:54:57Z · sase-1j6.2] PROPOSED FOLLOW-UP: test_child_identity_persists_and_publishes_one_local_machine_hood fails on the clean base tree (installed sase-core-rs wheel lacks autonomy_resolve_selection; needs just install-venv rebuild), unrelated to this phase

[2026-10-09T19:55:02Z · sase-1j6.2] PROPOSED FOLLOW-UP: test_registry_rebuild_keeps_live_identity_pending_claim flaked once under just check at load1>30 (passes alone and with neighboring suites); watch for repeats before filing a flake bead

[2026-10-09T19:55:11Z · sase-1j6.2] failure-facts done: runner_failure_facts (stdlib-only capture+prefilter) and runner_lifecycle_phase (breadcrumbs+boot identity) landed; marks wired at all 8 boundaries; facts persisted at all 5 failure writers; record_runner_error names code swaps. Verified: 26 new tests pass; neighboring suites 87 passed (1 pre-existing base failure recorded separately); lint gates incl symvision pass; tool-run check lane 54389 passed with 1 load flake that passes alone+combined. Boot capture ~140ms cold, memoized; prefilter epic-symbol re-keyed to sase-1j6.

## Dependencies

- **Blocks:** [sase-1j6.3](sase-1j6.3.md) ✓ · ⧖ 2026-10-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1j6.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.2/README.md) | [sase-1j6.2](sase-1j6.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6dd92ea`](https://github.com/sase-org/sase/commit/6dd92ea0e37f1ac2d4b2744062013833d6a60b38) | feat(auto-restart): runner boot identity, lifecycle crumbs, failure facts | [sase-1j6.2](sase-1j6.2.md) | 2026-10-09 15:56:34 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1j6.2][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1j6.2/README.md

<!-- sase:referenced-by:end -->
