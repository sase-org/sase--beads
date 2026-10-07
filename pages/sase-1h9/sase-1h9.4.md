# Bead: sase-1h9.4 — No terminal wait alert for superseded session members

[Bead Pages](../README.md) / [sase-1h9](README.md) / sase-1h9.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0xo](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0xo.md) · **Assignee:** `sase-1h9.4` · **Size:** small
**Created:** 2026-10-07 07:52:37 EDT · **Closed:** 2026-10-07 08:46:41 EDT
**Plan:** [202610/finalizer\_repair\_hardening.md](https://github.com/sase-org/sase--plans/blob/main/202610/finalizer_repair_hardening.md)

## Description

wait-terminal-alerts: limit wait_checks terminal-blocker detection to members that are really terminal, so a failed monitor whose follow-up turn launched (or any member superseded by a newer one) no longer raises a false "Wait dependency can never self-resolve" notification.

## Notes

[2026-10-07T12:46:15Z · sase-1h9.4] PROPOSED FOLLOW-UP: hood/adjacent wait suites fail identically on clean tree (agent_name_in_hood hits stale sase-core-rs content-layout wire schema 6 vs 7; same env cause fails 4 hood + 12 adjacent tests) — needs env/wire fix or suite repair, out of phase scope

[2026-10-07T12:46:41Z · sase-1h9.4] Limited terminal_blocking_artifacts_for_name/hood to newest failed member with no newer live member and no materialized launched monitor follow-up (new turn_followup_outcome on ArtifactCandidate; no sase-core equivalent query so Python-only). Verified: 3 new regression tests pass; 235 tests across 24 wait/wait_checks suites green; sase tool run check lint stages green except known master-red symvision (sase-1h6); 4 hood + 12 adjacent failures reproduce identically on clean tree (stale core wire env issue, recorded as follow-up).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h9.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h9.4/README.md) | [sase-1h9.4](sase-1h9.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`91e6c64`](https://github.com/sase-org/sase/commit/91e6c645728acceb8b64feeeddea8996587bc418) | fix(wait): stop terminal blockers alerting on superseded members | [sase-1h9.4](sase-1h9.4.md) | 2026-10-07 08:48:31 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1h9.4][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h9.4/README.md

<!-- sase:referenced-by:end -->
