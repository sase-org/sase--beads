# Bead: sase-12w.6.4.2 — Ratchet SASE onto the published sudo contracts

[Bead Pages](../README.md) / [sase-12w.6.4](sase-12w.6.4.md) / sase-12w.6.4.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-12w.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-12w.6.land.md) · **Assignee:** `sase-12w.6.4.2` · **Size:** medium
**Created:** 2026-09-18 19:35:04 EDT
**Plan:** [202609/publish\_detached\_sudo\_core.md](https://github.com/sase-org/sase--plans/blob/main/202609/publish_detached_sudo_core.md)

## Description

consumer-ratchet: after a complete non-yanked sase-core-rs release containing all sase-12w.6 Rust commits is published, advance the CI source pin, dependency floor, and lockfile to it and prove exact-floor binding plus focused sudo behavior.

## Notes

[2026-09-19T00:45:53Z · sase-12w.6.4.2] Consumer-ratchet is blocked on a complete non-yanked sase-core-rs PyPI package containing 4a8c6d4 (initgroups) plus 9bf272e/9e1ab3f/09f543b. PyPI latest is still incomplete 0.34.48 (no sdist). Tags v0.34.49–v0.34.58 exist but Release-plz macos universal2 fails with initgroups gid_t/u32 vs c_int. The ABI fix is on master AFTER v0.34.58; publish-plan builds from the tagged workspace version, so those runs still compile v0.34.58. sase_gateway has release=false and was omitted from sase_core changelog_include, so the gateway-only fix does not open v0.34.59. Landing release-plz.toml changelog_include += sase_gateway so the next release-plz-pr can tag a tree that includes the fix, then ratchet the SASE pin/floor/lock.

[2026-09-19T00:58:44Z · sase-12w.6.4.2] REMAINING: after changelog_include lands on sase-core master and Release-plz opens/merges a version whose tree contains 4a8c6d4, wait for a complete non-yanked PyPI sase-core-rs (sdist + linux x86_64/aarch64 + macos universal2). Then just ratchet-core-revision; raise pyproject.toml/uv.lock (ratchet-core-window will refuse while floor 0.34.48 lacks sdist — do the same narrowly scoped edit the tool enforces, then --check); prove exact-floor bindings with probe_core_floor/check_sase_core_rs_bindings; run focused sudo tests and just check; epic-symbols; close only this bead.

## Dependencies

- **Depends on:** [sase-12w.6.4.1](sase-12w.6.4.1.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12w.6.4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-12w.6.4.2/README.md) | [sase-12w.6.4.2](sase-12w.6.4.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@8b75bb0`](https://github.com/sase-org/sase-core/commit/8b75bb0b681a1baf6d0a87bd4e0c3a4af7a60bc9) | fix(release): include gateway commits in sase-core-rs changelog | [sase-12w.6.4.2](sase-12w.6.4.2.md) | 2026-09-18 21:00:07 EDT |
