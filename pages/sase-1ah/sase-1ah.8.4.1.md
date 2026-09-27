# Bead: sase-1ah.8.4.1 — Let release-plz select the gateway across a minor bump

[Bead Pages](../README.md) / [sase-1ah.8.4](sase-1ah.8.4.md) / sase-1ah.8.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ah.8.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ah.8.land.md) · **Assignee:** `sase-1ah.8.4.1` · **Size:** small
**Created:** 2026-09-26 18:37:51 EDT · **Closed:** 2026-09-26 18:49:34 EDT
**Plan:** [202609/receipt\_capable\_wheel.md](https://github.com/sase-org/sase--plans/blob/main/202609/receipt_capable_wheel.md)

## Description

unblock-core-release: drop the caret pin on the unpublished sase_gateway workspace path dependency so release-plz can cut the 0.35.0 release that contains the receipt binding.

## Notes

[2026-09-26T22:49:34Z · sase-1ah.8.4.1] Dropped the caret pin on sase_gateway workspace dep (now path-only) in sase-core Cargo.toml; cargo metadata reports sase_core_py requirement '*' with package version still 0.34.73; sase tool run check in sase-core passed (run 4c751b4aa4064cfd253227dd2de31056). Change left uncommitted for host-owned finalizer; release-plz dispatch is phase 2's job (sase-1ah.8.4.2).

## Dependencies

- **Blocks:** [sase-1ah.8.4.2](sase-1ah.8.4.2.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ah.8.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ah.8.4.1/README.md) | [sase-1ah.8.4.1](sase-1ah.8.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@89ad2e9`](https://github.com/sase-org/sase-core/commit/89ad2e93e61a881acd873da0b3f6bd3e4479f74e) | fix(build): drop version pin on sase\_gateway path dependency | [sase-1ah.8.4.1](sase-1ah.8.4.1.md) | 2026-09-26 18:56:23 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ah.8.4.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ah.8.4.1/README.md

<!-- sase:referenced-by:end -->
