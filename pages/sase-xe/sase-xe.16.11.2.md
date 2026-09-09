# Bead: sase-xe.16.11.2 — Share followed-family promotion decisions across frontends

[Bead Pages](../README.md) / [sase-xe.16.11](sase-xe.16.11.md) / sase-xe.16.11.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-xe.16.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.land.md) · **Assignee:** `sase-xe.16.11.2` · **Size:** medium
**Created:** 2026-09-09 04:38:27 EDT · **Closed:** 2026-09-09 05:31:10 EDT
**Plan:** [202609/remote\_dispatch\_landing\_remaining.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_landing_remaining.md)

## Description

core-follow-policy: move the followed-batch singleton-to-family promotion derivation added by sase-xe.16.9 into sase-core, preserving identity matching, ambiguous-family refusal, explicit-follow scope, and unfollow tombstones.

## Notes

[2026-09-09T09:30:34Z · sase-xe.16.11.2] Committed followed-batch family-promotion surface for the adapter phase. Schema version is 1 (FLEET_CONTRACT_SCHEMA_VERSION).

Exported sase_core_rs binding (dict-in/dict-out):
- fleet_followed_batch_family_promotions(request: dict) -> dict

Rust entry point: sase_core::followed_batch_family_promotions. Reuses FollowRecordWire, LogicalAgentLocatorWire, and FollowFamilyPromotionWire.

Unsupported schema_version or a non-dict envelope raises ValueError. Malformed follow records or observation locators also raise ValueError.

Request: {schema_version, records: [FollowRecordWire], observations: [LogicalAgentLocatorWire]}. Result: {schema_version, promotions: [FollowFamilyPromotionWire]}. Each promotion is {schema_version, from, to}. from must be a singleton; to must include family_id and keep origin, project_id, and agent_id.

Derivation rules: only explicit active singleton records are eligible; dispatch, pending, and already-family records are skipped; identity is (installation_id, project_id, agent_id); exactly one distinct family locator for that identity is required; duplicate observations of the same family locator are not ambiguous; a source locator is promoted at most once per request; singleton observations are ignored. Unfollow tombstones are not applied here — they continue to win in fleet_reconcile_follow_records.

TUI projection and off-thread persistence stay in Python. Do not ratchet sase-core-revision or replace Python followed_batch_family_promotions until this surface is published (setup-integration).

[2026-09-09T09:31:10Z · sase-xe.16.11.2] Moved followed-batch singleton-to-family promotion derivation into sase_core::fleet_follow_promotion with schema v1 dict binding fleet_followed_batch_family_promotions. Verified 12 Rust policy tests covering explicit singleton promotion, ambiguous-family refusal, dispatch/pending/family skip, origin/project/agent matching, redundant-source skip, non-TUI promotions accepted by reconcile_follow_records, and unfollow tombstones winning at reconciliation; plus the PyO3 envelope test; and scripts/check.sh fmt+clippy+workspace tests including PyO3.

## Dependencies

- **Depends on:** [sase-xe.16.11.1](sase-xe.16.11.1.md) ✓ · ⧖ 2026-09-09
- **Blocks:** [sase-xe.16.11.3](sase-xe.16.11.3.md) ○ · ⧖ 2026-09-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.11.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.11.2/README.md) | [sase-xe.16.11.2](sase-xe.16.11.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@06025ba`](https://github.com/sase-org/sase-core/commit/06025baef6985f7a84d997325f774468d8efcaca) | feat(core): derive followed-batch singleton-to-family follow promotions | [sase-xe.16.11.2](sase-xe.16.11.2.md) | 2026-09-09 05:32:12 EDT |
