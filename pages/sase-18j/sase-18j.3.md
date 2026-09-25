# Bead: sase-18j.3 — Pure classification, verdict, and failures aggregation in sase-core

[Bead Pages](../README.md) / [sase-18j](README.md) / sase-18j.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rq](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rq.md) · **Assignee:** `sase-18j.3` · **Size:** large
**Created:** 2026-09-24 19:07:05 EDT · **Closed:** 2026-09-24 21:28:21 EDT
**Plan:** [202609/tool\_e3\_failure\_triage.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e3_failure_triage.md)

## Description

core-classification: implement the witness-based NEW/KNOWN/FLAKY/UNKNOWN rule as a deterministic pure function with two tightening knobs, the failure-kind and legacy mapping, the verdict, REPEAT detection, owner matching, the store-backed stage and settle operations, and failures aggregation, in sase-core only.

## Notes

[2026-09-25T01:28:21Z · sase-18j.3] Core failure classification landed in sase-core. Verified: sase tool run check succeeded (run 31f00a6bfba5662a6a185f0a40fd3872, 216s). Targeted: 25 triage pure tests (DoD-4 a-j, knobs, owners, REPEAT, cross-project/machine, permutation, DoD-3 kinds/legacy/environment, verdict boundaries, fixtures), 17 store triage tests (stage/settle/show round trips, idempotence, KNOWN witness, control/infra suppression, failures aggregation/filters/isolation, owner lookup, unknown-field refusals), 2 telemetry binding round-trips (classify/verdict/stage/settle/show/failures) all green. Goldens added for classify/stage/settle/show/failures. epic-symbols clean.

## Dependencies

- **Depends on:** [sase-18j.2](sase-18j.2.md) ✓ · ⧖ 2026-09-24
- **Blocks:** [sase-18j.5](sase-18j.5.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18j.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-18j.3.md) | [sase-18j.3](sase-18j.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@321e7b4`](https://github.com/sase-org/sase-core/commit/321e7b4762ff461f189ce18281c8306e0fb9c0eb) | feat(triage): pure classification, verdict, stage/settle, and failures aggregation | [sase-18j.3](sase-18j.3.md) | 2026-09-24 21:30:41 EDT |
