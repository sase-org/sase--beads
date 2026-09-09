# Bead: sase-yy.3 — Durable operation identity in the link outbox

[Bead Pages](../README.md) / [sase-yy](README.md) / sase-yy.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09d.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09d.f1.md) · **Assignee:** `sase-yy.3` · **Size:** medium
**Created:** 2026-09-09 11:48:17 EDT · **Closed:** 2026-09-09 14:23:32 EDT
**Plan:** [202609/artifact\_link\_events\_v2.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_events_v2.md)

## Description

outbox-identity: give every queued link mutation a full-strength operation id, stop count-collapsing distinct operations, and define retirement semantics that compose with the per-root publication retry ledger.

## Notes

[2026-09-09T18:22:55Z · sase-yy.3] PROPOSED FOLLOW-UP: Ratchet published sase-core-rs floor when the complete wheel window catches up — this phase now uses artifact_link_event_* bindings; just check passes via the pinned/local core build but probe_core_floor still reports the declared 0.32.55 wheel floor as stale.

[2026-09-09T18:23:32Z · sase-yy.3] Implemented event-backed artifact-link outbox entries with 32-hex operation IDs, legacy row compatibility, pending event enumeration, and later-phase symvision markers; verified focused outbox/read pytest, validate_sase_core_rs, symvision, and just check.

## Dependencies

- **Depends on:** [sase-yy.2](sase-yy.2.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-yy.4](sase-yy.4.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-yy.5](sase-yy.5.md) ◐ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yy.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-yy.3/README.md) | [sase-yy.3](sase-yy.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fb89440`](https://github.com/sase-org/sase/commit/fb89440a55d1971bb0bb17934ef0ebace24ddeee) | feat(artifact-links): add operation-aware link outbox | [sase-yy.3](sase-yy.3.md) | 2026-09-09 14:25:28 EDT |
