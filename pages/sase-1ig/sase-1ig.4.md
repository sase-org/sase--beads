# Bead: sase-1ig.4 — Make the Rust dev-install recipes honest

[Bead Pages](../README.md) / [sase-1ig](README.md) / sase-1ig.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ym](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ym.md) · **Assignee:** `sase-1ig.4` · **Size:** small
**Created:** 2026-10-08 18:23:29 EDT · **Closed:** 2026-10-08 20:31:44 EDT
**Plan:** [202610/just\_install\_pypi\_dev\_venv.md](https://github.com/sase-org/sase--plans/blob/main/202610/just_install_pypi_dev_venv.md)

## Description

rust-recipes: make `rust-dev-install` write the core source stamp, make the `*-uv-tool` recipes fail when uv or the tool env is missing, give the rust recipes `[group('rust')]` and `[doc]`, and align `sase update --to dev`'s core step with the dev-update `rust-dev-install-uv-tool` shape.

## Notes

[2026-10-09T00:31:35Z · sase-1ig.4--1] PROPOSED FOLLOW-UP: tests/test_macro_terminology.py::test_macro_string_literals_avoid_xprompt_terms fails on this tree with tests/test_plugin_commands_mount.py: string '"xprompt"' (line 124 reserved-name assertion from committed 991c8b4dd7; file untouched by this phase, finding present in HEAD content, so reproduces identically on clean base). Corroborated on task bead sase-1hr (+1 recorded); guard allowlist needs an entry for the reserved-name assertion.

[2026-10-09T00:31:44Z · sase-1ig.4--1] All 4 rust-recipes clauses done and verified: (1) rust-dev-install stages+commits core source stamp (.sase-core-rs-source.json via pending file); (2) all *-uv-tool recipes exit 1 when uv or tool venv missing; (3) rust recipes carry [group(rust)]+[doc]; (4) sase update --to-dev core step now runs just rust-dev-install-uv-tool with dev-update profile env+timeout (models/plan/execute). Verified: tests/test_justfile_lint.py + tests/mode_switch/ 83 passed; just --list shows [rust] group. Full just check (monitor t4c4a4nbjhm6): 53840 passed, 6 failed = 1 NEW + 4 KNOWN + 1 FLAKY. The NEW failure (test_macro_string_literals_avoid_xprompt_terms, finding in unmodified tests/test_plugin_commands_mount.py, present in HEAD) reproduces identically on clean base; recorded as PROPOSED FOLLOW-UP citing task sase-1hr (+1 corroborated). epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1ig.1](sase-1ig.1.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1ig.8](sase-1ig.8.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ig.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ig.4.md) | [sase-1ig.4](sase-1ig.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e5c09c1`](https://github.com/sase-org/sase/commit/e5c09c19f58d159fdbcb8c0c00b3196a28a7675f) | feat(rust-recipes): make Rust dev-install recipes honest | [sase-1ig.4](sase-1ig.4.md) | 2026-10-08 20:33:02 EDT |
