# Bead: sase-rn.2 — Adopt the finalizer protocol core release

[Bead Pages](../README.md) / [sase-rn](README.md) / sase-rn.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08y](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08y.md) · **Assignee:** `sase-rn.2` · **Size:** small
**Created:** 2026-08-20 16:35:03 EDT · **Closed:** 2026-08-20 17:22:36 EDT
**Plan:** [202608/pluggable\_finalizers.md](https://github.com/sase-org/sase--plans/blob/main/202608/pluggable_finalizers.md)

## Description

core-adopt: raise the `sase-core-rs` dependency floor, refresh the lockfile, add the Python typed adapter and minimum-version smoke coverage, and keep all host-side work behind compatibility facades until the released binding is available.

## Notes

[2026-08-20T21:21:59Z · sase-rn.2] PROPOSED FOLLOW-UP: Fix stale admin_center_config_hub feature-flag removal — just check fails because closed flag bead sase-rk still has a registry/schema definition and surviving FeatureFlag references.

[2026-08-20T21:22:36Z · sase-rn.2] Added typed finalizer wire/facade adoption over sase-core-rs 0.29.5 and finalizer minimum-version probes; verified focused pytest, ruff, validate_sase_core_rs, and epic-symbols empty. just check was run and reached feature-flag lint, which failed on unrelated closed flag bead sase-rk retaining admin_center_config_hub; recorded proposed follow-up on this phase.

[2026-08-20T21:23:40Z · sase-rn.2] Verified focused finalizer facade tests, validate_sase_core_rs contract checks, no remaining epic symbols, and just check up to unrelated admin_center_config_hub flag lint blocker.

## Dependencies

- **Depends on:** [sase-rn.1](sase-rn.1.md) ✓ · ⧖ 2026-08-20
- **Blocks:** [sase-rn.3](sase-rn.3.md) ✓ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rn.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-rn.2/README.md) | [sase-rn.2](sase-rn.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8f82eb9`](https://github.com/sase-org/sase/commit/8f82eb99205cfb4f6b0db08f56d81ea0efa5bbfb) | feat(core): adopt finalizer protocol bindings | [sase-rn.2](sase-rn.2.md) | 2026-08-20 17:24:53 EDT |
