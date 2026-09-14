# Bead: sase-zw.8.1 — Adopt the Rust scratch owner and finish Cargo leak prevention

[Bead Pages](../README.md) / [sase-zw.8](sase-zw.8.md) / sase-zw.8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zw.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zw.land.md) · **Assignee:** `sase-zw.8.1` · **Size:** medium
**Created:** 2026-09-13 18:40:38 EDT · **Closed:** 2026-09-14 07:45:28 EDT
**Plan:** [202609/disk\_footprint\_remaining\_work.md](https://github.com/sase-org/sase--plans/blob/main/202609/disk_footprint_remaining_work.md)

## Description

scratch: replace the duplicate temp reaper with the existing Rust API, complete configurable horizons and the non-incremental core profile, and preserve isolated Cargo build directories.

## Dependencies

- **Blocks:** [sase-zw.8.2](sase-zw.8.2.md) ✓ · ⧖ 2026-09-13
- **Blocks:** [sase-zw.8.5](sase-zw.8.5.md) ◐ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zw.8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zw.8.1/README.md) | [sase-zw.8.1](sase-zw.8.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6a60ee5`](https://github.com/sase-org/sase/commit/6a60ee5fb7c924ffc9bbe0613660f18cc68cec19) | feat(managed-tmp): make reaper horizons and pressure limits configurable | [sase-zw.8.1](sase-zw.8.1.md) | 2026-09-14 07:39:12 EDT |
| sase-core | [`sase-core@244eb3f`](https://github.com/sase-org/sase-core/commit/244eb3fc7b25d3ec8aafb2d2a9b584b9d5b49109) | build(release): disable incremental compilation to preserve isolated build scratch directories | [sase-zw.8.1](sase-zw.8.1.md) | 2026-09-14 07:41:28 EDT |
