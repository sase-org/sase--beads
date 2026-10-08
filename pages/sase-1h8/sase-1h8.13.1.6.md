# Bead: sase-1h8.13.1.6 — Port links, +1 and snooze onto the mutation view

[Bead Pages](../README.md) / [sase-1h8.13.1](sase-1h8.13.1.md) / sase-1h8.13.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yi](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yi.md) · **Assignee:** `sase-1h8.13.1.6` · **Size:** medium
**Created:** 2026-10-08 14:46:07 EDT · **Closed:** 2026-10-08 19:11:03 EDT
**Plan:** [202610/finish\_read\_model\_mutations\_child\_epic.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_read_model_mutations_child_epic.md)

## Description

port-links-evidence: move links.rs (canonical targets, undirected holders, projections, receipts, provenance) and plus_one_snooze.rs (+1 evidence, promotions, snooze, cancel) onto the view with affected-row-only work, dual-mode tests and cached-path counters.

## Notes

[2026-10-08T23:11:03Z · sase-1h8.13.1.6] Ported links.rs (add/set-projections/remove incl. canonical targets, undirected holders, receipts) and plus_one_snooze.rs (+1 evidence/dedup/promotion, snooze/re-snooze, cancel, wake) onto MutationView: single algorithms over cached/replay backings, affected rows+streams only, publish-direct commit with reducer-truth corrections. Added tests/links_evidence.rs (10 tests: warm 1-sweep/0-replay/0-snapshot + bounded hydration/stream reads + token-only next reads + cache-equals-replay per entry point, error byte-stability, dual-mode cached-vs-replay parity). Verified: 203 bead::mutation tests, bead::read_model suite, bead_read_parity (35), bead_event_parity (16), bead_read_model_parity (6) all green; sase tool run check exit=0. No view.rs/publish/support edits; no PROPOSED FOLLOW-UPs.

## Dependencies

- **Depends on:** [sase-1h8.13.1.3](sase-1h8.13.1.3.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1h8.13.1.7](sase-1h8.13.1.7.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1h8.13.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1h8.13.1.6/README.md) | [sase-1h8.13.1.6](sase-1h8.13.1.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@dd1a67c`](https://github.com/sase-org/sase-core/commit/dd1a67c0727ecb98920955c454785fb0dc98a50c) | feat(beads): port links, +1 and snooze mutations onto the mutation view | [sase-1h8.13.1.6](sase-1h8.13.1.6.md) | 2026-10-08 19:12:02 EDT |
