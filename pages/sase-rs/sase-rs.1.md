# Bead: sase-rs.1 — Rust feature-flag preference store and bindings

[Bead Pages](../README.md) / [sase-rs](README.md) / sase-rs.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09g.md) · **Assignee:** `sase-rs.1` · **Size:** medium
**Created:** 2026-08-21 09:58:40 EDT · **Closed:** 2026-08-21 10:36:34 EDT
**Plan:** [202608/feature\_flag\_control\_center.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flag_control_center.md)

## Description

core: add a versioned, locked, atomic machine-state store for persistent feature-flag booleans in sase-core, expose strict PyO3 read and set bindings, and prove concurrency, corruption, downgrade, and durability behavior.

## Notes

[2026-08-21T14:36:17Z · sase-rs.1] Landed in sase-core c04a2192392cd0226baa68d83db17f2e148be9b2 (feat(core): add versioned feature-flag preference store) on master; bindings are feature_flag_state_get / feature_flag_state_set / feature_flag_state_wire_schema_version.

[2026-08-21T14:36:34Z · sase-rs.1] Verified in sase-core: cargo fmt --check, clippy -D warnings, and cargo test --workspace via just check. Store covers missing/corrupt/oversized/unsupported state without deletion, exclusive-lock RMW so concurrent writers keep distinct keys, pretty JSON atomic replace with temp cleanup, snake_case validation, unknown-key preservation, and PyO3 get/set JSON wire round trips. Commit c04a2192392cd0226baa68d83db17f2e148be9b2 is on sase-core master. No leftover --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-rs.2](sase-rs.2.md) ✓ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rs.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rs.1/README.md) | [sase-rs.1](sase-rs.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@c04a219`](https://github.com/sase-org/sase-core/commit/c04a2192392cd0226baa68d83db17f2e148be9b2) | feat(core): add versioned feature-flag preference store | [sase-rs.1](sase-rs.1.md) | 2026-08-21 10:35:08 EDT |
