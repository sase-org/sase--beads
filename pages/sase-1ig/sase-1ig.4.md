# Bead: sase-1ig.4 — Make the Rust dev-install recipes honest

[Bead Pages](../README.md) / [sase-1ig](README.md) / sase-1ig.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ym](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ym.md) · **Assignee:** `sase-1ig.4` · **Size:** small
**Created:** 2026-10-08 18:23:29 EDT
**Plan:** [202610/just\_install\_pypi\_dev\_venv.md](https://github.com/sase-org/sase--plans/blob/main/202610/just_install_pypi_dev_venv.md)

## Description

rust-recipes: make `rust-dev-install` write the core source stamp, make the `*-uv-tool` recipes fail when uv or the tool env is missing, give the rust recipes `[group('rust')]` and `[doc]`, and align `sase update --to dev`'s core step with the dev-update `rust-dev-install-uv-tool` shape.

## Dependencies

- **Depends on:** [sase-1ig.1](sase-1ig.1.md) ✓ · ⧖ 2026-10-08
- **Blocks:** [sase-1ig.8](sase-1ig.8.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ig.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ig.4.md) | [sase-1ig.4](sase-1ig.4.md) | 0 |
