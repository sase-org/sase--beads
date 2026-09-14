# Bead: sase-zw.8.2 — Make proc runtime retention bounded and safe against concurrent launches

[Bead Pages](../README.md) / [sase-zw.8](sase-zw.8.md) / sase-zw.8.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zw.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zw.land.md) · **Assignee:** `sase-zw.8.2` · **Size:** medium
**Created:** 2026-09-13 18:40:39 EDT · **Closed:** 2026-09-14 08:54:48 EDT
**Plan:** [202609/disk\_footprint\_remaining\_work.md](https://github.com/sase-org/sase--plans/blob/main/202609/disk_footprint_remaining_work.md)

## Description

procs: implement validated, age-bounded runtime retention in Rust, protect concurrent reservations, and run orphan cleanup on the hourly lane.

## Notes

[2026-09-14T12:22:54Z · sase-zw.8.2] PROPOSED FOLLOW-UP: Proc log retention cleanup - live ~/.sase/procs has 456 rowless .log files while runtime entries are row-aligned; this phase intentionally kept log cleanup to pruned rows only.

[2026-09-14T12:43:33Z · sase-zw.8.2] PROPOSED FOLLOW-UP: Unrelated just check baseline failures - after proc-runtime fixes, untouched checks still fail for agent_tag terminology, Justfile rust-dev-install lint, shell done writer allowlist, managed_tmp_reaper binding scan, and dismissed-agent save audit.

[2026-09-14T12:54:48Z · sase-zw.8.2] Implemented Rust-owned bounded proc runtime retention with Python, disk reap, config, and hourly chop wiring. Verified cargo test -p sase_core procs::runtime --lib; cargo test -p sase_core_py proc_store_bindings_round_trip_python_dicts_and_legacy_aliases --lib; focused pytest for proc runtime, disk preview, config schema, chop registration, and artifact audit; just _lint-symvision; final just check passed lint/install stages but scoped pytest still has 8 unrelated untouched baseline failures (agent_tag terminology, Justfile rust-dev-install lint, shell writer allowlist, dismissed save audit, managed_tmp_reaper binding scan). Live disposition: 456 rowless proc logs and 0 rowless runtime entries; log cleanup recorded as proposed follow-up.

## Dependencies

- **Depends on:** [sase-zw.8.1](sase-zw.8.1.md) ✓ · ⧖ 2026-09-13
- **Blocks:** [sase-zw.8.3](sase-zw.8.3.md) ◐ · ⧖ 2026-09-13
- **Blocks:** [sase-zw.8.5](sase-zw.8.5.md) ◐ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zw.8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zw.8.2/README.md) | [sase-zw.8.2](sase-zw.8.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6c433c1`](https://github.com/sase-org/sase/commit/6c433c14d1ec0accb17ea6357ebe1da0b4ea528b) | feat(procs): route runtime retention through Rust owner | [sase-zw.8.2](sase-zw.8.2.md) | 2026-09-14 08:56:21 EDT |
| sase-core | [`sase-core@bc78952`](https://github.com/sase-org/sase-core/commit/bc7895217b29b095de3fea339a1f437d2f32cc27) | feat(procs): add runtime retention owner | [sase-zw.8.2](sase-zw.8.2.md) | 2026-09-14 08:58:43 EDT |
