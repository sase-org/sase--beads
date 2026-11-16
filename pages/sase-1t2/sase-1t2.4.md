# Bead: sase-1t2.4 — One facts builder, occupant resolution, and \`sase agent hijack --explain\`

[Bead Pages](../README.md) / [sase-1t2](README.md) / sase-1t2.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1ct](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1ct.md) · **Assignee:** `sase-1t2.4` · **Size:** medium
**Created:** 2026-11-15 20:00:09 EST
**Plan:** [202611/agent\_hijack\_dependability.md](https://github.com/sase-org/sase--plans/blob/main/202611/agent_hijack_dependability.md)

## Description

facts_resolver: build one Python facts builder used by every hijack caller (no hard-coded facts), resolve names, session names, and session containers to the occupying member through the Rust occupant selection, and switch the stop orchestrator to the v2 decision. Add `sase agent hijack -e/--explain NAME` and the additive -j envelope keys, plus a screenshot-shaped fixture test.

## Dependencies

- **Depends on:** [sase-1t2.1](sase-1t2.1.md) ✓ · ⧖ 2026-11-15
- **Depends on:** [sase-1t2.2](sase-1t2.2.md) ✓ · ⧖ 2026-11-15
- **Blocks:** [sase-1t2.5](sase-1t2.5.md) ◐ · ⧖ 2026-11-15
- **Blocks:** [sase-1t2.6](sase-1t2.6.md) ◐ · ⧖ 2026-11-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1t2.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1t2.4/README.md) | [sase-1t2.4](sase-1t2.4.md) | 0 |
