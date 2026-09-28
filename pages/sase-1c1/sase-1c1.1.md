# Bead: sase-1c1.1 — Fix macOS path canonicalization in sase-core

[Bead Pages](../README.md) / [sase-1c1](README.md) / sase-1c1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ti](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ti.md) · **Assignee:** `sase-1c1.1` · **Size:** small
**Created:** 2026-09-28 07:09:23 EDT · **Closed:** 2026-09-28 08:57:19 EDT
**Plan:** [202609/master\_ci\_green\_and\_0\_18\_release.md](https://github.com/sase-org/sase--plans/blob/main/202609/master_ci_green_and_0_18_release.md)

## Description

core-macos: in the linked sase-core checkout, canonicalize the deepest existing ancestor in launch_scratch_liveness normalize_path, make the managed_tmp_roots test expect canonical storage, and add a symlink regression test that reproduces the macOS /var vs /private/var bug on Linux.

## Notes

[2026-09-28T12:57:19Z · sase-1c1.1--1] Verified: cargo test -p sase_core --lib launch_scratch_liveness+managed_tmp_roots, 18 passed incl 2 new regression tests (normalize_path deepest-existing-ancestor canonicalization, symlink-with-missing-suffix live-holder). Full sase tool run check timed out after 45m on release/dev builds but all lint/fmt/validation stages passed in retained log; no epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1c1.2](sase-1c1.2.md) ◐ · ⧖ 2026-09-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1c1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1c1.1.md) | [sase-1c1.1](sase-1c1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@1fee641`](https://github.com/sase-org/sase-core/commit/1fee6419181b69826724652d65d79258c66b8982) | fix(sase-core): canonicalize deepest existing ancestor in launch\_scratch\_liveness normalize\_path | [sase-1c1.1](sase-1c1.1.md) | 2026-09-28 08:58:31 EDT |
