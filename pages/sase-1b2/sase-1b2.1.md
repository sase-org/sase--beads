# Bead: sase-1b2.1 — finalizer\_status summary field on the Rust agent-scan wire

[Bead Pages](../README.md) / [sase-1b2](README.md) / sase-1b2.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sr](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sr.md) · **Assignee:** `sase-1b2.1` · **Size:** small
**Created:** 2026-09-27 05:49:29 EDT · **Closed:** 2026-09-27 06:10:00 EDT
**Plan:** [202609/agents\_tab\_final\_deck.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_tab_final_deck.md)

## Description

core-status-wire: in sase-core, add the tolerant FinalizerStatusSummaryWire and AgentMetaWire.finalizer_status, coerce it leniently in the scanner, bump the artifact-index schema with a no-op refresh migration, and cover parity and tolerance with tests.

## Notes

[2026-09-27T10:10:00Z · sase-1b2.1] core-status-wire done in sase-core: FinalizerStatusSummaryWire/Instance/Runner on the agent-scan wire with skip-when-None byte stability; tolerant scanner coercion (120-char caps, 16-instance cap, negative/NaN drops); index schema 33->34 with no-op v34 refresh migration; no fleet-contract leak. Verified: focused unit+parity tests pass (incl. 4 new tests), sase tool run check green (5f5a1b04).

## Dependencies

- **Blocks:** [sase-1b2.7](sase-1b2.7.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1b2.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1b2.1/README.md) | [sase-1b2.1](sase-1b2.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f4f2e96`](https://github.com/sase-org/sase-core/commit/f4f2e96a2e9ee1fdfffa8cbf935d6c77e61bc8ca) | feat(agent-scan): add tolerant finalizer\_status summary to scan wire | [sase-1b2.1](sase-1b2.1.md) | 2026-09-27 06:13:01 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1c][1] | Mapping sase-1b2 phase dependency graph for value report | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1c/README.md

<!-- sase:referenced-by:end -->
