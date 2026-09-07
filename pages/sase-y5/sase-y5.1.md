# Bead: sase-y5.1 — Define the shared subscription capacity model

[Bead Pages](../README.md) / [sase-y5](README.md) / sase-y5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.052](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.052.md) · **Assignee:** `sase-y5.1` · **Size:** medium
**Created:** 2026-09-07 16:09:19 EDT · **Closed:** 2026-09-07 16:45:36 EDT
**Plan:** [202609/subscription\_capacity.md](https://github.com/sase-org/sase--plans/blob/main/202609/subscription_capacity.md)

## Description

capacity-domain: Implement the Rust observation and public read contracts, validation, freshness, scope applicability, and summary rules specified in this plan, with deterministic fixtures and PyO3 coverage. No collection or UI.

## Notes

[2026-09-07T20:45:36Z · sase-y5.1] Implemented sase-core provider_usage observation and public schema v1: validation, remaining-percent derivation, 2C/4C freshness, declared scope matching, provider/model summaries, deterministic provider/window ties, and PyO3 exports. Fixture JSON covers 0/fractional/100/>100 used, shared+model windows, unknown scope, mixed ages, reset expiry, and ties. Core just check passed (fmt, clippy, workspace tests including provider_usage_bindings).

## Dependencies

- **Blocks:** [sase-y5.2](sase-y5.2.md) ◐ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-y5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-y5.1/README.md) | [sase-y5.1](sase-y5.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@07bd3bc`](https://github.com/sase-org/sase-core/commit/07bd3bc80be6cefba3643a36b74c1ebf2f6e6b20) | feat(provider-usage): add observation and public read contracts | [sase-y5.1](sase-y5.1.md) | 2026-09-07 16:55:07 EDT |
