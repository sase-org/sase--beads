# Bead: sase-14c.1 — Rust normalizer and weekly classification

[Bead Pages](../README.md) / [sase-14c](README.md) / sase-14c.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0o6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0o6.md) · **Assignee:** `sase-14c.1` · **Size:** medium
**Created:** 2026-09-20 12:41:09 EDT · **Closed:** 2026-09-20 13:15:52 EDT
**Plan:** [202609/muse\_usage\_windows.md](https://github.com/sase-org/sase--plans/blob/main/202609/muse_usage_windows.md)

## Description

core-normalizer: add the sase_core Muse subscription-usage normalizer, its PyO3 binding, and the indicator arm that classifies Muse's weekly window as a weekly all-model window.

## Notes

[2026-09-20T17:15:24Z · sase-14c.1] PROPOSED FOLLOW-UP: An absent Muse usage tick (authoritative_empty=true, per this epic's design) clears the stored Muse windows — store.rs merge_ok_observation wipes record.windows on any complete authoritative-empty observation — so a single probe tick whose echo mint misses the deadline blanks the header weekly indicator until the next successful tick (up to ~300s). Phase 2 should decide whether a deadline-miss should instead be a non-clearing outcome, or accept the blip knowingly.

[2026-09-20T17:15:52Z · sase-14c.1] Added sase-core provider_usage/muse.rs: normalize_muse_usage + ProviderUsageNormalizeMuseUsageRequestWire (schema-version check, validate_usage_observation exit, modelled on grok.rs). Live payload yields session (300min -> duration 18000s, period_start = resets_at - duration) and weekly (duration_seconds/period_start None) windows, both Account/Probe/Allowed, Complete, account_mode=subscription, plan=None (tier never persisted, asserted in a test). usedPercent is never clamped (validate_used_percent only rejects negative/non-finite; over-100 test passes). Absent usage member -> Ok + authoritative_empty + muse_usage_not_yet_observed, projects as healthy Ok with no windows/attention, never 0%. Malformed usage/missing/wrong-typed/out-of-range members -> structured Error/MalformedPayload/muse_usage_malformed; vendor values that fail observation validation degrade to the same structured error, while bad requests (wrong schema_version, bad clock/provider) still return Validation. indicator.rs is_weekly_window gained the provider==muse && key==weekly && Account arm. Re-exported from provider_usage/mod.rs and sase_core lib.rs; added py_provider_usage_normalize_muse_usage (provider_usage_normalize_muse_usage) plus its binding-inventory doc line in sase_core_py. Verified: just check in sase-core exits 0 on the final tree (fmt-check, clippy -D warnings, cargo test --workspace: 3972 passed, 0 failed) including 15 muse.rs unit tests, 5 projection-level indicator tests and the PyO3 binding round-trip test; mutation-checked that disabling the indicator arm fails 3 of the classification tests. Live Muse 1.3.0 schema re-read to confirm all SubscriptionUsage members are required. No crate versions or CHANGELOG touched. NOT done here (phase 2 prerequisites): the change is uncommitted in the sase-core working tree for the host finalizer, and sase-core-rs still has to land on master and be published by release-plz before sase's pyproject floor and sase-core-revision.txt can move.

## Dependencies

- **Blocks:** [sase-14c.2](sase-14c.2.md) ◐ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14c.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14c.1/README.md) | [sase-14c.1](sase-14c.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3cae8ef`](https://github.com/sase-org/sase-core/commit/3cae8ef9ed926a1d3fb88e8b455ee663c0c3f24f) | feat(provider\_usage): normalize Muse subscription usage and classify its weekly window | [sase-14c.1](sase-14c.1.md) | 2026-09-20 13:16:56 EDT |
