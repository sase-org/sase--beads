# Bead: sase-zw.4 — Stop the Rust dev-build target leak at its source

[Bead Pages](../README.md) / [sase-zw](README.md) / sase-zw.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ka](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ka.md) · **Assignee:** `sase-zw.4` · **Size:** medium
**Created:** 2026-09-12 13:26:43 EDT · **Closed:** 2026-09-12 17:06:22 EDT
**Plan:** [202609/bound\_sase\_disk\_footprint.md](https://github.com/sase-org/sase--plans/blob/main/202609/bound_sase_disk_footprint.md)

## Description

cargo: make the dev-update profile non-incremental, keep every dev-install entry point on a managed or repo-owned target root, and document the rule that agents never invent a CARGO_TARGET_DIR.

## Notes

[2026-09-12T21:06:22Z · sase-zw.4--1] Verified monitor failure cleanup: just _lint-symvision passed, tests/test_github_cli.py passed, just fmt passed, clean-env just check passed with full-suite escalation, and sase bead epic-symbols sase-zw.4 reported no entries.

## Dependencies

- **Blocks:** [sase-zw.7](sase-zw.7.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zw.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zw.4.md) | [sase-zw.4](sase-zw.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`edaf35b`](https://github.com/sase-org/sase/commit/edaf35bd95fd9312a3704e0e8ddf7830cbdcdeb6) | fix(rust): keep dev builds in managed targets | [sase-zw.4](sase-zw.4.md) | 2026-09-12 17:09:13 EDT |
