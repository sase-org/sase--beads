# Bead: sase-1pt.8 — Prove latency and sidecar reliability on athena

[Bead Pages](../README.md) / [sase-1pt](README.md) / sase-1pt.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.15z](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.15z.md) · **Assignee:** `sase-1pt.8` · **Size:** medium
**Created:** 2026-10-29 18:11:08 EDT · **Closed:** 2026-10-30 02:44:01 EDT
**Plan:** [202610/commit\_stage\_async\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202610/commit_stage_async_publication.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:9ee3e3420293f5b9d4e45d18 | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

prove: after the installed sase includes the epic, measure commit-stage latency against the baseline and audit every sampled run's sidecar obligations end to end.

## Notes

[2026-10-30T06:43:16Z · sase-1pt.8] Prove results (athena, Oct 28-30, n=54 no-conflict single-repo on current installed pre-epic code): model~done median 346.5s p95 562.1s; finalizer-phase p95 802.9s; publication substep median 255.4s dominates, create_commit 2.6s; exec tail median 58.4s. Targets MISSED: finalizer p95 +742.9s, model-done median +286.5s, queue-age UNMEASURABLE (publisher never ran). Installed sase 0.18.1+173.g5437e0baa LACKS refby-events/deferred-parity/publisher/enqueue-only (workspace e69360f49d has all). Obligations audited: 78/78 committing runs pushed (SHAs), 8 clean-tree skips correct; hood DONE terminal on sampled agents; prompt archives listed; release evidence recorded; 13 link events pending for 2/6 sampled runs (durable, not loss); refby 83 active/77 quarantined untouched (replay uninstalled, correct); 5 pre-resolver pin-only conflicts went model-repair 28min-2.6h, 0 pin-only trials since resolver; retention stamp 2026-10-30T05:42Z enforced. Full report: file:explicit:9ee3e3420293f5b9d4e45d18

[2026-10-30T06:43:33Z · sase-1pt.8] PROPOSED FOLLOW-UP: reinstall sase on athena past e69360f49d (needs human approval; no /sase_gate created because a gate turn would end the single-turn prove run before bead close), then collect >=30 (plan: 100 or 72h) no-conflict runs and re-run this measurement to prove the <60s targets and queue-age p95 <10min — detail: current install 0.18.1+173.g5437e0baa lacks 4/7 epic phases, 0 runs on new code, heartbeat absent

[2026-10-30T06:43:38Z · sase-1pt.8] PROPOSED FOLLOW-UP: coordinate prove re-measurement with sase-1nf.11 hood-quarantine drain — 3,527 quarantined hood rows inflate every inline drain scan and lock contention, masking the epic signal; cites sase-1nf.11

[2026-10-30T06:43:44Z · sase-1pt.8] PROPOSED FOLLOW-UP: re-audit referenced-by backlog after install — 83 active + 77 quarantined rows predate convert_backlog=yes replay; verify cites events emitted and rows acknowledged — detail: backlog correctly untouched while replay uninstalled

[2026-10-30T06:43:49Z · sase-1pt.8] PROPOSED FOLLOW-UP: watch first pin-only conflict on resolver-containing code — 5 pre-resolver pin-only repairs (28min-2.6h) motivated the resolver but no pin-only trial has occurred since it landed; confirm descendant-SHA auto-resolution fires

[2026-10-30T06:44:01Z · sase-1pt.8] Measured, not yet proven: installed sase 0.18.1+173.g5437e0baa lacks 4/7 epic phases so 0 runs on new code; pre-epic baseline n=54 no-conflict single-repo median 346.5s p95 562.1s (targets missed, residuals + follow-ups on bead); obligations audited end-to-end (78/78 pushes, hood terminal, archives listed, release evidence recorded, pin/refby/retention checked); report file:explicit:9ee3e3420293f5b9d4e45d18; epic-symbols clean; no memory/bead changes (decision_record=no honored)

## Dependencies

- **Depends on:** [sase-1pt.3](sase-1pt.3.md) ✓ · ⧖ 2026-10-29
- **Depends on:** [sase-1pt.4](sase-1pt.4.md) ✓ · ⧖ 2026-10-29
- **Depends on:** [sase-1pt.7](sase-1pt.7.md) ✓ · ⧖ 2026-10-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pt.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pt.8/README.md) | [sase-1pt.8](sase-1pt.8.md) | 0 |
