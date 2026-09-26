# Bead: sase-19o.1 — Registry rebuilds keep in-flight claims

[Bead Pages](../README.md) / [sase-19o](README.md) / sase-19o.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0s9.md) · **Assignee:** `sase-19o.1` · **Size:** medium
**Created:** 2026-09-25 13:51:10 EDT · **Closed:** 2026-09-25 15:19:49 EDT
**Plan:** [202609/bead\_work\_registry\_drift\_resilience.md](https://github.com/sase-org/sase--plans/blob/main/202609/bead_work_registry_drift_resilience.md)

## Description

registry-inflight-claims: make rebuild_name_registry() (both the optimistic _commit_rebuild_locked path and the _rebuild_name_registry_locked fallback) carry forward prior local artifact-backed claims whose artifact dir is identity-pending (bootstrap agent_meta.json only, no name/clan/session yet) while its runner process is alive, re-derive entries for dirs whose named metadata landed after the unlocked scan, and keep dropping claims whose dir is gone, dead, or names a different identity. Share one per-artifact derivation helper between the full scan and the carry-forward. Add regression tests for the incident sequence.

## Notes

[2026-09-25T19:19:21Z · sase-19o.1] PROPOSED FOLLOW-UP: Investigate the scoped check baseline failures (21 unrelated tests failed after 47,486 passed; all formatting and lint stages, including Symvision, passed, while the focused registry rebuild suite passed).

[2026-09-25T19:19:49Z · sase-19o.1] Implemented locked carry-forward for live identity-pending artifact claims in both rebuild paths; added race, liveness, removal, renamed-identity, and clan regression coverage. Focused registry suite passed (40 tests); full recorded check passed all format/lint stages but its scoped suite had 21 unrelated failures after 47,486 passes, recorded as a proposed follow-up.

## Dependencies

- **Blocks:** [sase-19o.3](sase-19o.3.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19o.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19o.1/README.md) | [sase-19o.1](sase-19o.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9d79a73`](https://github.com/sase-org/sase/commit/9d79a73462b0e5287dc4731067d1ff81dbe509ae) | fix(agent-names): retain live in-flight registry claims | [sase-19o.1](sase-19o.1.md) | 2026-09-25 15:21:04 EDT |
