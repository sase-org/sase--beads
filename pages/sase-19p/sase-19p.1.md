# Bead: sase-19p.1 — Close attribution and close facts in the touch index (sase-core)

[Bead Pages](../README.md) / [sase-19p](README.md) / sase-19p.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0s0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0s0.md) · **Assignee:** `sase-19p.1` · **Size:** medium
**Created:** 2026-09-25 14:05:29 EDT · **Closed:** 2026-09-25 15:03:44 EDT
**Plan:** [202609/agent\_closed\_beads.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_closed_beads.md)

## Description

core: stamp issue_closed events with the acting closer plus a durable closed_by payload field, credit closes in the touch-index reducer (with legacy same-instant note recovery), add a per-touch close record with resolution/reason/standing, and bump the index schema.

## Notes

[2026-09-25T19:03:23Z · sase-19p.1] PROPOSED FOLLOW-UP: Reopen attribution still stamps created_by — open_issue and reopen_closed_ancestors credit the bead creator instead of the acting reopener (out of scope for core phase)

[2026-09-25T19:03:44Z · sase-19p.1] core phase done in sase-core: closed_by payload + actor stamping (incl. forced/delegated), CLI parity with SASE_AGENT=1 guard, touch-index crediting + close record + schema 3, fixtures updated; sase tool run check green (286s), no epic-symbol leftovers

## Dependencies

- **Blocks:** [sase-19p.2](sase-19p.2.md) ✓ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19p.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19p.1/README.md) | [sase-19p.1](sase-19p.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@7677abd`](https://github.com/sase-org/sase-core/commit/7677abd82df9019350af294dd47915ac4eb23aef) | feat(bead): record close attribution and close facts in touch index | [sase-19p.1](sase-19p.1.md) | 2026-09-25 15:04:57 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-19o.3--1][1] | Need whether this phase bumped scan schema to 10 | 1 |
| read-by | [agent:sase-19p.1][2] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19o.3.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-19p.1/README.md

<!-- sase:referenced-by:end -->
