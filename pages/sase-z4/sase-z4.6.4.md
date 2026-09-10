# Bead: sase-z4.6.4 — Prove packaged compatibility and integrated weighted workloads

[Bead Pages](../README.md) / [sase-z4.6](sase-z4.6.md) / sase-z4.6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-z4.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z4.land.md) · **Assignee:** `sase-z4.6.4` · **Size:** medium
**Created:** 2026-09-10 08:15:43 EDT · **Closed:** 2026-09-10 12:55:46 EDT
**Plan:** [202609/weighted\_capacity\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/weighted_capacity_landing_repairs.md)

## Description

release-acceptance: establish real published package floors, add wheel-only compatibility checks and end-to-end workload coverage, and resolve the existing retired rollout flag bead.

## Notes

[2026-09-10T16:55:12Z · sase-z4.6.4] PROPOSED FOLLOW-UP: Resolve existing retired rollout flag bead sase-z5 - this phase verified no weighted_queue_capacity tracked source/doc references, but the launch instruction allowed closing only sase-z4.6.4.

[2026-09-10T16:55:46Z · sase-z4.6.4] Verified core floor probe ok at 0.33.0; main focused tests passed; main just check passed after scoped gate escalated to full suite; plugin just test-wheel and just check passed; negative install rejects sase==0.17.1; weighted_queue_capacity has no tracked source/doc references; left existing flag bead sase-z5 open per instruction to close only this bead.

## Dependencies

- **Depends on:** [sase-z4.6.3](sase-z4.6.3.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z4.6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-z4.6.4/README.md) | [sase-z4.6.4](sase-z4.6.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4f6eb2b`](https://github.com/sase-org/sase/commit/4f6eb2b173aacb3f4aeb954753fb57aefcb01f10) | deps(core): ratchet weighted capacity floor | [sase-z4.6.4](sase-z4.6.4.md) | 2026-09-10 12:57:36 EDT |
