# Bead: sase-16h.2 — Record child process facts and authorize reaping in sase-core

[Bead Pages](../README.md) / [sase-16h](README.md) / sase-16h.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pf](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pf.md) · **Assignee:** `sase-16h.2` · **Size:** medium
**Created:** 2026-09-22 13:05:40 EDT · **Closed:** 2026-09-22 14:53:01 EDT
**Plan:** [202609/tool\_e15\_enforced\_adoption.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e15_enforced_adoption.md)

## Description

core-child-facts: add the sase-core wire, store write, and binding that persist a running run's child pid, pgid, and process identity, extend reconcile to return identity-matched reap candidates, and move sase's core revision pin past that commit.

## Notes

[2026-09-22T18:51:26Z · sase-16h.2] PROPOSED FOLLOW-UP: Ratchet sase-core-revision.txt past the sase-core observe commit once host finalizers land and push it (phase sase-16h.3 needs tool_run_observe from CI-built core)

[2026-09-22T18:51:56Z · sase-16h.2] PROPOSED FOLLOW-UP: just check symvision flags agent_env_refusal_reason in src/sase/service/platform.py on an untouched file (pre-existing, fails the lint gate for unrelated agents)

[2026-09-22T18:52:18Z · sase-16h.2] PROPOSED FOLLOW-UP: sase-core just check shows 3 sase_gateway fleet flakes (fleet_attention_read_empty, fleet_enrollment_and_hello, fleet_launch_replays_delayed_launch) that pass alone under just test -p sase_gateway

[2026-09-22T18:52:25Z · sase-16h.2] PROPOSED FOLLOW-UP: sase-core just check shows 3 sase_gateway fleet flakes (fleet_attention_read_empty, fleet_enrollment_and_hello, fleet_launch_replays_delayed_launch) that pass alone under just test -p sase_gateway

[2026-09-22T18:53:01Z · sase-16h.2] core-child-facts done: sase-core observe wire/store/binding persists child pid+pgid+identity on the running row, finish repeats idempotently, reconcile returns identity-matched reap candidates only for dead wrappers with recorded facts; sase adapter + smoke round trip + symvision whitelist keyed to sase-16h. Verified: 36 sase_core tool_run tests, 3 sase_core_py telemetry tests, 18+62 focused sase tests, smoke, ruff/mypy clean, core fmt/clippy clean. just check red only on pre-existing platform.py symvision flag (untouched file); core just check red only on 3 gateway fleet flakes that pass alone. Pin ratchet left to land agent (no pushed core commit yet); epic-symbols empty for this phase.

## Dependencies

- **Depends on:** [sase-16h.1](sase-16h.1.md) ✓ · ⧖ 2026-09-22
- **Blocks:** [sase-16h.3](sase-16h.3.md) ✓ · ⧖ 2026-09-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16h.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16h.2/README.md) | [sase-16h.2](sase-16h.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d163dfa`](https://github.com/sase-org/sase/commit/d163dfa2b6db768a04a7814d1bb306c121fd8736) | feat(tool): add tool\_run\_observe adapter, smoke round trip, and symvision epic whitelist | [sase-16h.2](sase-16h.2.md) | 2026-09-22 15:00:28 EDT |
| sase-core | [`sase-core@4b536cd`](https://github.com/sase-org/sase-core/commit/4b536cdcf28dc3fd75f411c3b4b0467c9174d2ce) | feat(tool): add tool\_run observe core, reap wire types, and telemetry binding | [sase-16h.2](sase-16h.2.md) | 2026-09-22 15:06:08 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16h.2][1] | Confirm follow-up notes landed before closing | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16h.2/README.md

<!-- sase:referenced-by:end -->
