# Bead: sase-16z.9.1 — Fix sase-16z landing defects in sase

[Bead Pages](../README.md) / [sase-16z.9](sase-16z.9.md) / sase-16z.9.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-16z.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16z.land.md) · **Assignee:** `sase-16z.9.1` · **Size:** medium
**Created:** 2026-09-23 16:32:20 EDT
**Plan:** [202609/usage\_collection\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_collection_landing_fixes.md)

## Description

landing-fixes: resolve the three epic-introduced symvision failures (reuse resolve_provider_cli_command in refresh readiness; privatize the capability-cache dir/invalidate helpers), make executable_fingerprint resolve bare commands through PATH so agy/grok cache entries hit, classify rate limits on JSON-line transport failures, stop 429 matching decimals, remove the stale real-CLI chop test, keep the inline crash path from overwriting finished providers, keep a failed Models-panel reservation read from ending tracking early, and fix stale comments, a test name, and the axe.md opt-out key.

## Dependencies

- **Blocks:** [sase-16z.9.3](sase-16z.9.3.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.9.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.9.1/README.md) | [sase-16z.9.1](sase-16z.9.1.md) | 0 |
