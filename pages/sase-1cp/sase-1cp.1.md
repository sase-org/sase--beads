# Bead: sase-1cp.1 — Rust duration class, inline fit, and calibration

[Bead Pages](../README.md) / [sase-1cp](README.md) / sase-1cp.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u2.md) · **Assignee:** `sase-1cp.1` · **Size:** medium
**Created:** 2026-09-29 16:47:59 EDT · **Closed:** 2026-09-29 17:06:50 EDT
**Plan:** [202609/tool\_inline\_routing.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_inline_routing.md)

## Description

core-duration-class: in sase-core, add the optional duration_class catalog field (validated, excluded from the definition digest), the class-floor table, and the fit and calibration functions with PyO3 bindings and tests.

## Notes

[2026-09-29T21:06:50Z · sase-1cp.1] core-duration-class done in sase-core checkout (uncommitted, host lands): ToolDurationClassWire + optional duration_class on ToolDefinitionWire (deny_unknown_fields kept, schema v1, digest excludes it); new tool_run/duration.rs with short=0s/long=600s/unbounded-none floors, duration_fit (ceiling 0 errors, floor==ceiling refused) and duration_calibration (silent below 10 samples, floor_above_typical->short, typical_meets_floor->long, bounded_evidence); bindings tool_run_duration_fit + tool_run_duration_calibration in telemetry domain; golden fixture definition_duration_long.json. Verified: just fast ok, 11 duration + 9 catalog + binding round-trip tests pass, full sase tool run check in core checkout succeeded (run 9b21e564, 268s). No epic-symbol entries. sase repo untouched; no commit per host-owned completion.

## Dependencies

- **Blocks:** [sase-1cp.3](sase-1cp.3.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1cp.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cp.1/README.md) | [sase-1cp.1](sase-1cp.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@17b072b`](https://github.com/sase-org/sase-core/commit/17b072b34f69fee4b97ea8a90157f51fc3d3e15c) | feat(tool-run): add duration classes and inline-fit policy | [sase-1cp.1](sase-1cp.1.md) | 2026-09-29 17:08:19 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1cp.1][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1cp.1/README.md

<!-- sase:referenced-by:end -->
