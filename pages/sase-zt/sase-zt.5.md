# Bead: sase-zt.5 — Live admission and display smoke

[Bead Pages](../README.md) / [sase-zt](README.md) / sase-zt.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.06.f0` · **Assignee:** `sase-zt.5` · **Size:** xsmall
**Created:** 2026-09-12 10:33:32 EDT · **Closed:** 2026-09-12 17:39:55 EDT
**Plan:** [202609/queue\_capacity\_budget.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_budget.md)

## Description

verify: launch real agents against a lowered runner limit to confirm a high-capacity launch is admitted, a low-capacity launch drains first, and both render the intended badge and accent.

## Notes

[2026-09-12T21:39:13Z · sase-zt.5] PROPOSED FOLLOW-UP: Agent-side LaunchApproval handoff crashes after creating a pending gate — running `sase run` from a SASE agent created LaunchApproval bundles, then failed importing `maybe_handoff_gate_from_agent` from `sase.gate_shell`, leaving pending launch notifications instead of a clean handoff.

[2026-09-12T21:39:55Z · sase-zt.5] Verified live queue-capacity smoke with temporary runner limit lowered from existing override 8 to 1 and restored to 8 afterward. Host-style launches showed zt5-smoke-high with authored queue_capacity=100 admitted/running while occupied capacity exceeded the global limit; zt5-smoke-low with queue_capacity=1 parked with runner_effective_limit=1, runner_admission_limit=1, insufficient-capacity blocker, and zt5-smoke-high listed as a slot holder. Invalid prompts failed with the expected migration messages for %q:0 and %q(capacity=1, w=2). Smoke agents were stopped after sampling. Ran sase bead epic-symbols sase-zt.5 immediately before close: no --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-zt.3](sase-zt.3.md) ✓ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zt.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zt.5.md) | [sase-zt.5](sase-zt.5.md) | 0 |
