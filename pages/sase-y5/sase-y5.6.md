# Bead: sase-y5.6 — Collect Grok subscription allowance through ACP

[Bead Pages](../README.md) / [sase-y5](README.md) / sase-y5.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.052](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.052.md) · **Assignee:** `sase-y5.6` · **Size:** medium
**Created:** 2026-09-07 16:09:23 EDT · **Closed:** 2026-09-08 07:53:56 EDT
**Plan:** [202609/subscription\_capacity.md](https://github.com/sase-org/sase--plans/blob/main/202609/subscription_capacity.md)

## Description

grok-usage: Implement the Grok Build ACP billing extension collector, native percentage and verified legacy decoding, account-wide scope, honest unsupported and not-applicable states, and bounded process cleanup with fixture coverage.

## Notes

[2026-09-08T11:53:56Z · sase-y5.6] Implemented the Grok Build ACP collector (grok agent stdio, initialize, _x.ai/billing) with native creditUsagePercent weekly windows, verified monthlyLimit/used legacy ratio, account-wide scope, Build identity check, and honest unsupported/not-applicable/unauthenticated/malformed/partial states. Isolated fake-CLI tests cover wire method, identity mismatch, ineligible Free/Enterprise and API-key evidence, missing period/percentage, and descendant process reaping. just check passed (lint gates + 518-file scoped tests). No --epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-y5.11](sase-y5.11.md) ◐ · ⧖ 2026-09-07
- **Depends on:** [sase-y5.3](sase-y5.3.md) ✓ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-y5.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-y5.6/README.md) | [sase-y5.6](sase-y5.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0f71004`](https://github.com/sase-org/sase/commit/0f71004c5a4aaf12558d6b50934eec602e15084d) | feat(llm): collect Grok subscription allowance through ACP | [sase-y5.6](sase-y5.6.md) | 2026-09-08 07:55:21 EDT |
