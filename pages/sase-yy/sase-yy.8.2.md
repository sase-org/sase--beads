# Bead: sase-yy.8.2 — Require durable owners and publish complete event files atomically

[Bead Pages](../README.md) / [sase-yy.8](sase-yy.8.md) / sase-yy.8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-yy.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.land.md) · **Assignee:** `sase-yy.8.2` · **Size:** large
**Created:** 2026-09-10 14:27:24 EDT · **Closed:** 2026-09-10 16:38:33 EDT
**Plan:** [202609/artifact\_link\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/artifact_link_landing_repairs.md)

## Description

publication_durability: prevent false acknowledgements for missing owners, preserve non-document operations, install event files atomically across process death, and route manual document mutations through hidden machine stores with synchronous publication.

## Notes

[2026-09-10T20:31:35Z · sase-yy.8.2] PROPOSED FOLLOW-UP: just check is currently blocked by pre-existing feature-flag rule 8: live flag bead sase-z0 has no registry definition for key link_events; add the registry definition or close the bead.

[2026-09-10T20:34:26Z · sase-yy.8.2] PROPOSED FOLLOW-UP: just _lint-symvision is currently blocked by stale Justfile --epic-symbol entries for closed bead sase-z7.3: UsagePeekSnapshot, cached_usage_display_snapshot, and cached_usage_indicator_projection; remove those stale entries and clean up the symbols.

[2026-09-10T20:37:22Z · sase-yy.8.2] PROPOSED FOLLOW-UP: the escalated full pytest lane surfaced unrelated fleet/core contract failures: tests/test_fleet_contract_counts_sase_core_rs.py::test_count_contract_deduplicates_current_instances_and_buckets and three tests/ace/tui/test_agents_fleet_refresh_laziness.py cases; reconcile the fleet summary row_kind/family_role contract before relying on full-suite green.

[2026-09-10T20:38:33Z · sase-yy.8.2] Implemented durable artifact-link publication ownership receipts, atomic event-object installation, machine-local ownerless event storage, machine-store routing for manual mutations and plan inlet publication, fsynced outbox rewrites/appends, and focused coverage for the new durability behavior. Verification: core just check passed with PYO3_PYTHON/LD_LIBRARY_PATH pointing at the workspace venv Python; just install passed with isolated CARGO_TARGET_DIR; validate_sase_core_rs, check_sase_core_rs_bindings, focused artifact-link/validator pytest, validation, committed-plan validation, pyscripts, test-waits, changelog, terminology, and toobig checks passed. just check remains blocked by pre-existing feature-flag rule 8 for sase-z0/link_events and stale sase-z7.3 symvision epic-symbol entries; the escalated full pytest lane additionally surfaced unrelated fleet/core contract failures, all recorded above as proposed follow-ups.

## Dependencies

- **Depends on:** [sase-yy.8.1](sase-yy.8.1.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-yy.8.3](sase-yy.8.3.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-yy.8.4](sase-yy.8.4.md) ✓ · ⧖ 2026-09-10
- **Blocks:** [sase-yy.8.5](sase-yy.8.5.md) ✓ · ⧖ 2026-09-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-yy.8.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-yy.8.2.md) | [sase-yy.8.2](sase-yy.8.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`811700b`](https://github.com/sase-org/sase/commit/811700bc3830558df0db9ff7eaefecb2b6e7614b) | fix(artifact-links): require durable publication receipts | [sase-yy.8.2](sase-yy.8.2.md) | 2026-09-10 16:42:07 EDT |
| sase-core | [`sase-core@da0a738`](https://github.com/sase-org/sase-core/commit/da0a73895ff8d5aa3597df4abb3fe6004c443489) | feat(artifact-links): add publication ownership receipts | [sase-yy.8.2](sase-yy.8.2.md) | 2026-09-10 16:45:16 EDT |
