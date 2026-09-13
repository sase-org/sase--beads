# Bead: sase-zn.9.2 — Finish safe disk-pressure reaping in the Rust core

[Bead Pages](../README.md) / [sase-zn.9](sase-zn.9.md) / sase-zn.9.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zn.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zn.land.md) · **Assignee:** `sase-zn.9.2` · **Size:** medium
**Created:** 2026-09-12 17:29:03 EDT · **Closed:** 2026-09-12 18:58:49 EDT
**Plan:** [202609/finish\_ace\_typing\_lag.md](https://github.com/sase-org/sase--plans/blob/main/202609/finish_ace_typing_lag.md)

## Description

scratch_pressure: preserve fresh children and live build scratch, implement the missing free-space trigger, and integrate newer bucket coverage through a thin Python adapter.

## Notes

[2026-09-12T22:58:49Z · sase-zn.9.2] Implemented Rust-core managed tmp reaper with size and low-free-space pressure triggers, fresh-descendant/live-build preservation, Python adapter/chop/docs/tests, and run_gh export fix. Verified cargo test -p sase_core managed_tmp, cargo clippy -p sase_core -p sase_core_py --all-targets -- -D warnings, refreshed PyO3 wheel plus 32 focused Python tests, and SASE_CORE_DIR-pinned just check passed with scoped lane escalated to full suite.

## Dependencies

- **Blocks:** [sase-zn.9.3](sase-zn.9.3.md) ✓ · ⧖ 2026-09-12
- **Blocks:** [sase-zn.9.4](sase-zn.9.4.md) ✓ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zn.9.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zn.9.2/README.md) | [sase-zn.9.2](sase-zn.9.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`70b018b`](https://github.com/sase-org/sase/commit/70b018b91ae4b93dac9011612b33fde6dab4f34e) | feat(chop): harden managed temp pressure reaping | [sase-zn.9.2](sase-zn.9.2.md) | 2026-09-13 04:45:51 EDT |
| sase-core | [`sase-core@a64c40d`](https://github.com/sase-org/sase-core/commit/a64c40dfc3719eefcbadb6a5869adb28f0158806) | feat: Finish safe disk-pressure reaping in the Rust core (sase-zn.9.2) | [sase-zn.9.2](sase-zn.9.2.md) | 2026-09-13 04:46:20 EDT |
