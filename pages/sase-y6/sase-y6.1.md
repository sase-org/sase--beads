# Bead: sase-y6.1 — Rust notification store +1 model and upsert

[Bead Pages](../README.md) / [sase-y6](README.md) / sase-y6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.05k](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.05k.md) · **Assignee:** `sase-y6.1` · **Size:** medium
**Created:** 2026-09-07 17:06:57 EDT · **Closed:** 2026-09-07 17:37:56 EDT
**Plan:** [202609/ci\_watch\_notification\_plus\_one.md](https://github.com/sase-org/sase--plans/blob/main/202609/ci_watch_notification_plus_one.md)

## Description

core: add plus-one entries and a dedup key to the Rust notification row, an append-plus-one operation, and an atomic create-or-plus-one/supersede upsert with parity tests.

## Notes

[2026-09-07T21:37:56Z · sase-y6.1] Rust notification store plus-one model and upsert landed in sase-core: additive NotificationPlusOneWire/plus_ones/plus_ones_dropped/dedup_key on schema v1 (empty values skip-serialize; unknown fields still parse), append_notification_plus_one by id or (sender, dedup_key), upsert_notification create-or-plus-one with supersede retirement, PyO3 bindings, and parity tests for round-trip, legacy defaults, upsert branches, dismissed/snoozed match, 500-entry cap, cursor/state invariance, and concurrent append-vs-upsert. sase-core just fmt and clippy are green; cargo test --workspace is green (57 notification_store_parity tests plus notification_plus_one_and_upsert_bindings_round_trip). No --epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-y6.2](sase-y6.2.md) ◐ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-y6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-y6.1/README.md) | [sase-y6.1](sase-y6.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@a86bb91`](https://github.com/sase-org/sase-core/commit/a86bb91bf4978925d98b877688af3298fe408d96) | feat(notifications): add plus-one entries, dedup key, and create-or-plus-one upsert | [sase-y6.1](sase-y6.1.md) | 2026-09-07 17:39:43 EDT |
