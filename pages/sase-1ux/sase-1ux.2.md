# Bead: sase-1ux.2 — Consume the held state in sase and keep the held flag truthful

[Bead Pages](../README.md) / [sase-1ux](README.md) / sase-1ux.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1f4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1f4.md) · **Assignee:** `sase-1ux.2` · **Size:** medium
**Created:** 2026-11-22 08:33:06 EST
**Plan:** [202611/failed\_clan\_visibility.md](https://github.com/sase-org/sase--plans/blob/main/202611/failed_clan_visibility.md)

## Description

held-state: bucket `held` as Failed but nonterminal and never in flight. Show the member as `NOT ADOPTED ‖` with no ticking clock, move it to the settled monitor lane, and route the filesystem fallback loaders through the binding. Make every not-adopted path set the durable held flag and every successful readopt clear it.

## Dependencies

- **Depends on:** [sase-1ux.1](sase-1ux.1.md) ✓ · ⧖ 2026-11-22
- **Blocks:** [sase-1ux.3](sase-1ux.3.md) ◐ · ⧖ 2026-11-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ux.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ux.2/README.md) | [sase-1ux.2](sase-1ux.2.md) | 0 |
