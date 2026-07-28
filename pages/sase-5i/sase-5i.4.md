# Bead: sase-5i.4 — Phase 4: Rust core context, detector, builder, and vectors

[Bead Pages](../README.md) / [sase-5i](README.md) / sase-5i.4

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-5i.4`
**Created:** 2026-07-07 20:11:33 UTC · **Closed:** 2026-07-07 21:10:57 UTC
**Plan:** [202607/vcs\_ref\_colon\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202607/vcs_ref_colon_completion.md)

## Description

Repo: sase-core. Add VcsRef context/wire types, v2/v3 catalog tolerance, detector precedence, pure candidate/edit builder, and mirrored golden vectors.

## Notes

COMMIT: f27936565

[2026-07-27T21:38:51Z · sase-a1.land] [2026-07-07T21:10:00Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Implemented Rust VcsRef wire/context detection, pure ref candidate/edit builder with namespace chaining, v2/v3 catalog parsing tolerance, and golden-vector coverage in sase-core. Verified with cargo test --workspace and cargo clippy --workspace --all-targets -- -D warnings.

## Dependencies

- **Depends on:** [sase-5i.1](sase-5i.1.md) ✓
- **Blocks:** [sase-5i.5](sase-5i.5.md) ✓
