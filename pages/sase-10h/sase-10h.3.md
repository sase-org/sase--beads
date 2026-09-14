# Bead: sase-10h.3 — Epic-launch monitor carries explicit weight 0 and full-capacity acceptance

[Bead Pages](../README.md) / [sase-10h](README.md) / sase-10h.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.fa](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.fa.md) · **Assignee:** `sase-10h.3` · **Size:** medium
**Created:** 2026-09-13 19:13:27 EDT · **Closed:** 2026-09-13 21:06:21 EDT
**Plan:** [202609/gate\_admission\_never\_blocks\_approval.md](https://github.com/sase-org/sase--plans/blob/main/202609/gate_admission_never_blocks_approval.md)

## Description

epic-monitor-zero-weight: author queue_weight 0 on the epic-launch monitor member only, keep general monitor claim lineage intact, check capacity presentation, and add fakey end-to-end acceptance for tale/epic approval and rejection at a full weighted limit.

## Notes

[2026-09-14T01:06:21Z · sase-10h.3] Authored explicit queue_weight 0 on the epic-launch monitor only (StartMonitorRequest.queue_weight -> create_monitor_member override after inheritance). General monitors still inherit parent weight and runner_claim_owner_key. Fallback proc path still has no queue_weight. Made explicit 0 a valid record weight in the scanner/fleet/admission projection (record_weight_is_valid) so a live 0-weight monitor is not fail-closed as invalid; implicit 0/negative/NaN still fail closed. Zero-weight rows do not inflate occupied_capacity or render a w0 badge. Verified: unit inherit vs override; start_monitor inherit 2.0 and author 0.0; epic-launch request.queue_weight==0; proc fallback has no queue_weight; scan+TUI enrichment of explicit 0; occupied_capacity stays 1.0 with a 0-weight monitor at limit 1. Fakey: epic-launch-shaped monitor starts at cap 2 with occupant 1.0, phase-worker 1.0 admits, extra 1.0 parks; tale approve at cap 1 completes with no waiting.json and the coder parks then admits when capacity frees; parametrized approve/reject at full cap still complete; general weight-2 monitor still holds/transfers its inherited claim. just check lint gates passed; cargo clippy -p sase_core -D warnings clean; cargo test explicit_zero (6/6). epic-symbols: none.

## Dependencies

- **Depends on:** [sase-10h.1](sase-10h.1.md) ✓ · ⧖ 2026-09-13
- **Depends on:** [sase-10h.2](sase-10h.2.md) ✓ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-10h.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-10h.3.md) | [sase-10h.3](sase-10h.3.md) | 0 |
