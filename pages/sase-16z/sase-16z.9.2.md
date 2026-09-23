# Bead: sase-16z.9.2 — sase-core: per-provider polling floors in the usage indicator projection

[Bead Pages](../README.md) / [sase-16z.9](sase-16z.9.md) / sase-16z.9.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-16z.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16z.land.md) · **Assignee:** `sase-16z.9.2` · **Size:** small
**Created:** 2026-09-23 16:32:21 EDT · **Closed:** 2026-09-23 16:46:27 EDT
**Plan:** [202609/usage\_collection\_landing\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_collection_landing_fixes.md)

## Description

core-indicator-floors: in the linked sase-core repo, add an optional serde-defaulted `provider_min_intervals` map to the usage indicator projection request, validated like the floor-aware store read, and compute each window's freshness from `max(cadence_seconds, floor)` for providers that name a floor. Requests without the field must project exactly as today.

## Notes

[2026-09-23T20:46:27Z · sase-16z.9.2] sase-core: UsageIndicatorProjectionRequestWire gains optional serde-defaulted provider_min_intervals, validated by shared store validate_floor_map; project_provider_entries uses max(cadence,floor) for freshness/attention. Requests without the field project identically (golden test). New core tests (legacy/empty-map parity, floored-fresh vs unfloored-stale at age 200/cadence 60/floor 300, invalid-floor rejections) plus sase_core_py binding test all pass; sase tool run check succeeded. Changes left uncommitted in linked sase-core checkout for host finalizers.

## Dependencies

- **Blocks:** [sase-16z.9.3](sase-16z.9.3.md) ◐ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.9.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.9.2/README.md) | [sase-16z.9.2](sase-16z.9.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@1a2a752`](https://github.com/sase-org/sase-core/commit/1a2a752ff499015642215888ecf3b11f2c1c0c34) | feat(provider-usage): support per-provider minimum freshness floor in usage indicator projection | [sase-16z.9.2](sase-16z.9.2.md) | 2026-09-23 16:48:12 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16z.9.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-16z.9.2/README.md

<!-- sase:referenced-by:end -->
