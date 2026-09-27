# Bead: sase-1aq.10.7.5.7.3 — Prove settled stop, fresh-row stop, and retry-after-kill live from Athena

[Bead Pages](../README.md) / [sase-1aq.10.7.5.7](sase-1aq.10.7.5.7.md) / sase-1aq.10.7.5.7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.sase-1aq.10.7.5.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1aq.10.7.5.land.md) · **Assignee:** `sase-1aq.10.7.5.7.3` · **Size:** medium
**Created:** 2026-09-27 02:20:37 EDT · **Closed:** 2026-09-27 04:51:28 EDT
**Plan:** [202609/1aq\_receipts\_matched\_live\_proof.md](https://github.com/sase-org/sase--plans/blob/main/202609/1aq_receipts_matched_live_proof.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:1b071b131efc527dce16b7a1 | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

receipt_live_proof: drive Athena over SSH against Apollo on the matched build to prove the exact_ops_receipts contract live, and attach audited requirement-to-evidence notes to the original beads.

## Notes

[2026-09-27T08:50:31Z · sase-1aq.10.7.5.7.3] PROPOSED FOLLOW-UP: land the uncommitted sase-core claims-cache fix (crates/sase_core/src/host_liveness.rs) and redeploy both hosts via supported update to reconverge builds

[2026-09-27T08:50:47Z · sase-1aq.10.7.5.7.3] PROPOSED FOLLOW-UP: gateway precondition refusals (stale revision, capability-missing on dead rows) surface on the controller as uncertain after a full retry window instead of a terminal refusal — safe but slow

[2026-09-27T08:51:01Z · sase-1aq.10.7.5.7.3] PROPOSED FOLLOW-UP: consider writing the active artifact-index row at launch-accept so the 30s launch-receipt overlay window overlaps index availability (index currently lands ~30s+ after accept)

[2026-09-27T08:51:28Z · sase-1aq.10.7.5.7.3] receipt_live_proof verified live on matched builds (sase 48c3e0ddc + core b57cd21): probe-7 fresh exact stop at 79s settled/applied in 11s; probe-5 stop settled in ~10s with byte-identical already_settled same-key replay and unchanged Apollo journal; killed rows keep retry+fork; 3 same-key retries -> exactly one .r0, all settled; stale/cross-project guards refuse safely with no new-key resubmission; gateway restart preserves rows+receipts. Evidence file:explicit:1b071b131efc527dce16b7a1; notes on sase-xe.16.11, sase-xe.16.11.7.14.6.7.6, sase-1aq.10.7.5.2. In-phase sase-core claims-cache fix (uncommitted, Apollo .so only) filed as PROPOSED FOLLOW-UP for landing. cargo: host_liveness 13 ok, fleet_presentation 18 ok, gateway overlay 1 ok. Panes clean.

## Dependencies

- **Depends on:** [sase-1aq.10.7.5.7.2](sase-1aq.10.7.5.7.2.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1aq.10.7.5.7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1aq.10.7.5.7.3/README.md) | [sase-1aq.10.7.5.7.3](sase-1aq.10.7.5.7.3.md) | 0 |
