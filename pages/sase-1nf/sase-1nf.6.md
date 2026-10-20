# Bead: sase-1nf.6 — sase-core partial bead link projection and per-endpoint receipts

[Bead Pages](../README.md) / [sase-1nf](README.md) / sase-1nf.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.12i](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.12i.md) · **Assignee:** `sase-1nf.6` · **Size:** medium
**Created:** 2026-10-20 13:36:14 EDT · **Closed:** 2026-10-20 15:12:23 EDT
**Plan:** [202610/athena\_apollo\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/athena_apollo_audit_fixes.md)

## Description

links-core: add a skip mode to bead link projections that applies valid requests and reports missing holders per request, and extend the artifact-link publication receipt with per-endpoint outcomes and an acknowledged, parked, or pending disposition.

## Notes

[2026-10-20T18:42:38Z · sase-1nf.6--3] Updating replay mutation goldens because links-core adds the specified per-request link_projection_outcomes field; check failures showed six scenarios differed only by that intended additive result field.

[2026-10-20T19:12:23Z · sase-1nf.6--4] Implemented bead-link projection skip outcomes and per-endpoint publication receipts/bindings with regression coverage; sase tool run check passed (run 063f5f8528cc89e5815758c9394aeb57), and epic-symbols reported no leftovers.

## Dependencies

- **Blocks:** [sase-1nf.7](sase-1nf.7.md) ◐ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.6.md) | [sase-1nf.6](sase-1nf.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@ce6104b`](https://github.com/sase-org/sase-core/commit/ce6104b19cf36a8c71267c67c1afa0b52ac4c8ec) | feat(artifact-links): add partial projection receipts | [sase-1nf.6](sase-1nf.6.md) | 2026-10-20 15:13:16 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1nf.6--4][1] | Verify the phase is closed and its final note is recorded | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.6.md

<!-- sase:referenced-by:end -->
