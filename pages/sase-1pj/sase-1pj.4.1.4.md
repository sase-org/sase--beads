# Bead: sase-1pj.4.1.4 — Stage launch requests and agent-origin run requests

[Bead Pages](../README.md) / [sase-1pj.4.1](sase-1pj.4.1.md) / sase-1pj.4.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pj.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pj.4.md) · **Assignee:** `sase-1pj.4.1.4` · **Size:** medium
**Created:** 2026-10-29 14:37:30 EDT · **Closed:** 2026-10-29 23:16:08 EDT
**Plan:** [202610/gate\_staging.md](https://github.com/sase-org/sase--plans/blob/main/202610/gate_staging.md)

## Description

launch-cli: retain launch preview and continuation validation while returning staged descriptors from launch request and agent-origin run.

## Notes

[2026-10-30T03:15:39Z · sase-1pj.4.1.4] PROPOSED FOLLOW-UP: test_sase_sudo_skill_teaches_reviewed_request_contract still expects "ends your current turn by killing this process" after sase-1pj.4.1.3 dual-state sase_sudo.md rewrite — fails on HEAD independently of launch-cli

[2026-10-30T03:15:46Z · sase-1pj.4.1.4] PROPOSED FOLLOW-UP: tests/test_suite_gate_scoped_integration.py nested sandboxes miss tests/_agent_artifact_marker_audit_helpers.py (sase-1pu.3) so test_over_budget_selection_escalates_rather_than_queueing_for_a_lease and sibling scoped-run tests fail with ModuleNotFoundError on HEAD

[2026-10-30T03:15:53Z · sase-1pj.4.1.4] PROPOSED FOLLOW-UP: tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection stale (drops tests/test_core_finalizer_handoff.py) — already noted on sase-1pj.4.1.2 / sase-1ng

[2026-10-30T03:16:08Z · sase-1pj.4.1.4] Agent-origin sase launch request and sase run stage through run_gate_entry when staged_handoffs is on (common JSON descriptor, no notify/bundle/intent/spawn); human-origin still publishes; auto/max_slots/continuation/second-handoff fail before publication; typed_plan and requester continuation survive publish_staged_gate (approve/reject/timeout/stopped); flag-off still publishes and hands off. sase_run skill dual-state previewed via sase skill init --diff (not deployed). Focused pytest 15/15 plus prior 50-test launch/gate/sudo set green. just check remaining NEW/FLAKY are base-tree (sudo skill contract, suite-gate helper copy, stale contract_manifest) recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-1pj.4.1.3](sase-1pj.4.1.3.md) ✓ · ⧖ 2026-10-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pj.4.1.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.4.1.4/README.md) | [sase-1pj.4.1.4](sase-1pj.4.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9394107`](https://github.com/sase-org/sase/commit/9394107ac222be1e4972aa8a3bcae0a9a7a7a56f) | feat(gate): stage launch requests and agent-origin run | [sase-1pj.4.1.4](sase-1pj.4.1.4.md) | 2026-10-29 23:18:15 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pj.4.1.4][1] | Need the phase scope and current notes before continuing launch-cli | 4 |
| read-by | [agent:sase-1pj.4.1.land][2] | Need the child scope and notes | 1 |
| read-by | [agent:sase-1pj.5.1.3][3] | Need confirm the existing skill contract test follow-up before citing it | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.4.1.4/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.4.1.land/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pj.5.1.3/README.md

<!-- sase:referenced-by:end -->
