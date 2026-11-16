# Bead: sase-1t2.8.1.3 — Apply latches at adoption, retry, and run completion

[Bead Pages](../README.md) / [sase-1t2.8.1](sase-1t2.8.1.md) / sase-1t2.8.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1t2.8](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1t2.8.md) · **Assignee:** `sase-1t2.8.1.3` · **Size:** medium
**Created:** 2026-11-16 04:09:08 EST · **Closed:** 2026-11-16 09:04:09 EST
**Plan:** [202611/hijack\_latch\_boundaries.md](https://github.com/sase-org/sase--plans/blob/main/202611/hijack_latch_boundaries.md)

## Description

runner_boundaries: enforce latches under staged adoption and successor-delivery locks, at in-process and spawned retries, and at no-handoff completion; retain suppressed payloads and prevent replay.

## Notes

[2026-11-16T14:03:37Z · sase-1t2.8.1.3] PROPOSED FOLLOW-UP: symvision flags reset_lower_macros_cache (config/local_trust_enforcement.py) and reset_project_identity_caches (config/local_trust_management.py) as unused public symbols; both reproduce identically on the clean base tree (verified via stash) and come from sase-1t3.3 trust-memo work, not this phase

[2026-11-16T14:04:09Z · sase-1t2.8.1.3] runner_boundaries landed: latch checkpoints at staged adoption (apply+suppress under adoption lock), adoption replay/restoration (HijackLatchedError, no replay), in-process successor (apply+suppress before identity mutation), spawned/in-process retry (refuse + re-raise, guarded retry spawn), detached delivery (pre-submit latch observe), and run-end moot (real outcome kept); finalize preserves applied latch recovery. Verified: 3 new tests in tests/test_agent_hijack_runner_boundaries.py pass; latch/lock-order/spawn-guard/followup/staged/retry suites pass (51 total); ruff+mypy+fmt clean; sase tool run check clean except 2 symvision items proven pre-existing on clean tree (recorded as PROPOSED FOLLOW-UP)

## Dependencies

- **Depends on:** [sase-1t2.8.1.2](sase-1t2.8.1.2.md) ✓ · ⧖ 2026-11-16
- **Blocks:** [sase-1t2.8.1.4](sase-1t2.8.1.4.md) ◐ · ⧖ 2026-11-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.8.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.8.1.3/README.md) | [sase-1t2.8.1.3](sase-1t2.8.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`13b7ae9`](https://github.com/sase-org/sase/commit/13b7ae9075e96781c3d53480420a885b9f028b85) | feat(agent-hijack): enforce runner-side latch at adoption, retry, and delivery boundaries | [sase-1t2.8.1.3](sase-1t2.8.1.3.md) | 2026-11-16 09:08:06 EST |
