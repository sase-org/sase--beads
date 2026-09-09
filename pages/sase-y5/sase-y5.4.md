# Bead: sase-y5.4 — Collect Claude subscription windows and passive updates

[Bead Pages](../README.md) / [sase-y5](README.md) / sase-y5.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.052](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.052.md) · **Assignee:** `sase-y5.4` · **Size:** medium
**Created:** 2026-09-07 16:09:21 EDT · **Closed:** 2026-09-08 09:09:07 EDT
**Plan:** [202609/subscription\_capacity.md](https://github.com/sase-org/sase--plans/blob/main/202609/subscription_capacity.md)

## Description

claude-usage: Implement the zero-inference Claude usage probe and supplementary rate_limit_event capture, account-mode detection, conservative date parsing, per-window merges, and noninterference tests for normal stream parsing.

## Notes

[2026-09-08T13:08:27Z · sase-y5.4] PROPOSED FOLLOW-UP: Ratchet the published sase-core-rs floor to 0.32.43 — probe_core_floor reports provider_usage_* bindings exist in release v0.32.43 while pyproject still declares 0.32.42.

[2026-09-08T13:09:07Z · sase-y5.4] Implemented Claude zero-inference /usage collection and passive rate_limit_event capture; verified with focused usage/completion tests and passing just check.

## Dependencies

- **Blocks:** [sase-y5.11](sase-y5.11.md) ✓ · ⧖ 2026-09-07
- **Depends on:** [sase-y5.3](sase-y5.3.md) ✓ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-y5.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-y5.4/README.md) | [sase-y5.4](sase-y5.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cc58987`](https://github.com/sase-org/sase/commit/cc58987c2bab268906eb48f8ebe7688637ad8807) | feat(usage): collect Claude subscription windows | [sase-y5.4](sase-y5.4.md) | 2026-09-08 10:42:10 EDT |
