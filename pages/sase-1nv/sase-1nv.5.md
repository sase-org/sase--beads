# Bead: sase-1nv.5 — Prove recovery on both hosts and close recovery-proof

[Bead Pages](../README.md) / [sase-1nv](README.md) / sase-1nv.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.13m](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.13m.md) · **Assignee:** `sase-1nv.5` · **Size:** medium
**Created:** 2026-10-24 07:01:33 EDT
**Plan:** [202610/unblock\_sase\_1nf.md](https://github.com/sase-org/sase--plans/blob/main/202610/unblock_sase_1nf.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:0ad1354ad22ce3480a1a422c | attached via sase artifact create --bead |
| related | file:explicit:ddc1ff91f98de4e168df0d63 | attached via sase artifact create --bead |
| related | research:202610/publication_recovery_acceptance.md | Records the installed repair results, acceptance checks, canary outcomes, and remaining check-1 blocker |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

<!-- sase:links:end -->

## Description

pub-closeout: install the fixes on both hosts, run the repair, prove checks 1 and 5 under the chosen canary policy, update the acceptance report, then close sase-1nf.10.1.9.1 and sase-1nf.10.1.9.

## Notes

[2026-10-24T16:01:02Z · sase-1nv.5] PROPOSED FOLLOW-UP: Fix canonical turn gate routing — the documented turn block currently falls through to direct gate creation and fails missing_gate_turn_row; the legacy shell alias is a workaround.

[2026-10-24T22:12:10Z · sase-1nv.5--j] PHASE UPDATE: Both hosts expose --repair-revisions at SASE c594443dc / core 7ec12d2d7; report-first repairs completed with matching dated-backup hashes, and evidence is attached as file:explicit:0ad1354ad22ce3480a1a422c plus research:202610/publication_recovery_acceptance.md. Natural check 5 passed for agent 13y. Check 1 remains missing: Athena timed out before page materialization; Apollo bob-cli selected an active unknown row and hit a090a3a2c rebase conflict; Apollo SASE selected an active other row and failed page materialization with revision mismatch. No further retries or batch were run. PROPOSED FOLLOW-UP: Make bounded retry selection honor the requested historical error class — the Apollo attempts selected unrelated active rows, so sase-1nf.11 should review selection before its bounded drain and keep check 1 missing until a named request publishes.

[2026-10-26T22:01:50Z · sase-1nv.5] PHASE UPDATE (2026-10-26): Audited the 24 October acceptance report and complete evidence file:explicit:ddc1ff91f98de4e168df0d63. Check 1 remains missing; all three limit-1 calls failed and no batch was run. Fresh version probes show both hosts at SASE f4591e9106830fb5e558d71f506b4a2d9fe9791b / core d14a32c8242aea936f39711a8452ef0ba08b121d; default-forwarded Apollo SSH still authenticates as bbugyi200. Current Rust selection intentionally processes active rows ahead of stopped error-class matches, and its preferred_key falls through when missing/ineligible. No production retries, repairs, or installs were performed. Following the explicit remaining-work instruction, authored and validated child epic sase_plan_finish_publication_recovery_proof.md: additive exact-key core policy, CLI integration, readiness/replay and candidate ledger, three serialized host/project proofs, and acceptance reporting. Approval explicitly supplies one new exact limit-1 invocation per target; no batches. Its land agent closes only this enclosing phase after proof; ancestor closure stays with the owning land agents. Existing repair and check-5 evidence are retained. epic-symbols for sase-1nv.5 is empty.

## Dependencies

- **Depends on:** [sase-1nv.2](sase-1nv.2.md) ✓ · ⧖ 2026-10-24
- **Depends on:** [sase-1nv.4](sase-1nv.4.md) ✓ · ⧖ 2026-10-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nv.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nv.5.md) | [sase-1nv.5](sase-1nv.5.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nv.5--j][1] | Need the phase scope, notes, and design file before resuming work | 4 |
| read-by | [agent:sase-1nv.5.1.1][2] | Need the enclosing phase and its remaining work | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nv.5.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1nv.5.1.1/README.md

<!-- sase:referenced-by:end -->
