# Bead: sase-y5.7 — Supervise and coalesce refreshes across clients

[Bead Pages](../README.md) / [sase-y5](README.md) / sase-y5.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.052](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.052.md) · **Assignee:** `sase-y5.7` · **Size:** medium
**Created:** 2026-09-07 16:09:24 EDT · **Closed:** 2026-09-08 08:58:11 EDT
**Plan:** [202609/subscription\_capacity.md](https://github.com/sase-org/sase--plans/blob/main/202609/subscription_capacity.md)

## Description

usage-refresh: Implement the shared durable refresh service, per-provider admission and receipts, deadlines, cadence/backoff, scheduled collection, and best-effort limit/reset triggers. Verify overlapping requests and crash recovery.

## Notes

[2026-09-08T12:57:45Z · sase-y5.7] PROPOSED FOLLOW-UP: publish sase-core-rs with admit/due/backoff bindings and raise the SASE sase-core-rs floor — local rust-install exposes provider_usage_admit_refresh/refresh_due/mark_refresh_due/record_refresh_attempt; published 0.32.42 does not, and 0.32.43 only covers the store APIs.

[2026-09-08T12:58:11Z · sase-y5.7] Verified shared submit_usage_refresh coalesces overlapping provider subsets, joins without dropping peers, honors flag/config opt-out, marks due for limit-event and future disable-expiry, runs synthetic probes through the durable runner with 3-wide/10s/30s bounds and deadline leftovers, AXE usage_refresh chop no-ops when nothing is due, ACE first-paint fallback is pump-free, epic-symbols for sase-y5.7 are clean, core clippy -D warnings and provider_usage tests pass, and just check (full-suite escalation) passed.

## Dependencies

- **Depends on:** [sase-y5.3](sase-y5.3.md) ✓ · ⧖ 2026-09-07
- **Blocks:** [sase-y5.8](sase-y5.8.md) ◐ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-y5.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-y5.7/README.md) | [sase-y5.7](sase-y5.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`a0ac015`](https://github.com/sase-org/sase/commit/a0ac015e0bda1d0cc1e1eeb859e92e2f0314cdfe) | feat(llm): add shared subscription usage refresh service | [sase-y5.7](sase-y5.7.md) | 2026-09-08 09:23:27 EDT |
