# Bead: sase-1i5.9.1.2.1.2 — Repair host provenance fixtures, foreign-commit recovery, and detached-run isolation

[Bead Pages](../README.md) / [sase-1i5.9.1.2.1](sase-1i5.9.1.2.1.md) / sase-1i5.9.1.2.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1i5.9.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1i5.9.1.2.md) · **Assignee:** `sase-1i5.9.1.2.1.2` · **Size:** medium
**Created:** 2026-10-08 14:54:13 EDT · **Closed:** 2026-10-08 16:17:10 EDT
**Plan:** [202610/release\_master\_and\_full\_ci.md](https://github.com/sase-org/sase--plans/blob/main/202610/release_master_and_full_ci.md)

## Description

host-contracts: make gate and launch provenance assertions exact, resolve foreign-commit recovery without relaxing publication guards, and investigate the detached-run database lock with isolated evidence.

## Notes

[2026-10-08T20:17:01Z · sase-1i5.9.1.2.1.2--1] PROPOSED FOLLOW-UP: joined sase tool run check (run 89e8da85fbc501ea84a328cc496795b9) timed out after 45m with exit -9 and 48 KNOWN, verdict undetermined; re-run full check/Full CI under phase sase-1i5.9.1.2.1.7 to confirm the release tip

[2026-10-08T20:17:10Z · sase-1i5.9.1.2.1.2--1] host-contracts done. Verified: 59 passed across test_plan_gates_execution, test_plan_gates_action_api, test_plan_approval_actions_archive, test_finalizers_discard_guard_before_head (incl. new test_post_dispatch_unpushed_foreign_race_still_fails); 33 passed across test_gate_cli_answer_detach, axe/test_agent_meta_atomic, test_multi_prompt_launcher_macro_groups, tool/test_detach; ruff clean on all 6 touched files; sase bead epic-symbols clean. Provenance is exact: _gate_source/_gate_caller are never persisted in option results or translations (only decided_by/decided_via), asserted absent in execution, action-api, and archive tests; plan_approval_actions strips private gate keys before the decisions early-return. Published post-dispatch foreign-commit race is exempt while unpushed foreign race (refused with ahead-of-upstream error) and revert (still a discard) fail closed, resolving the failure mode tracked by sase-1hs (left open). Joined full check run timed out at 45m (exit -9, 48 KNOWN, undetermined; infra ceiling, no deterministic failure in scope) and is recorded as a follow-up note for phase sase-1i5.9.1.2.1.7; no ancestor closed.

## Dependencies

- **Blocks:** [sase-1i5.9.1.2.1.5](sase-1i5.9.1.2.1.5.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1i5.9.1.2.1.7](sase-1i5.9.1.2.1.7.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1i5.9.1.2.1.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1i5.9.1.2.1.2.md) | [sase-1i5.9.1.2.1.2](sase-1i5.9.1.2.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1914591`](https://github.com/sase-org/sase/commit/1914591ab497811326ce621d3015ecb15709b9b5) | fix(host-contracts): exact gate provenance, foreign-commit recovery, detached-run isolation | [sase-1i5.9.1.2.1.2](sase-1i5.9.1.2.1.2.md) | 2026-10-08 16:18:53 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1i5.9.1.2.1.2--1][1] | Need the phase scope and design file | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1i5.9.1.2.1.2.md

<!-- sase:referenced-by:end -->
