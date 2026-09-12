# Bead: sase-zw.4 — Stop the Rust dev-build target leak at its source

[Bead Pages](../README.md) / [sase-zw](README.md) / sase-zw.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ka](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ka.md) · **Assignee:** `sase-zw.4` · **Size:** medium
**Created:** 2026-09-12 13:26:43 EDT
**Plan:** [202609/bound\_sase\_disk\_footprint.md](https://github.com/sase-org/sase--plans/blob/main/202609/bound_sase_disk_footprint.md)

## Description

cargo: make the dev-update profile non-incremental, keep every dev-install entry point on a managed or repo-owned target root, and document the rule that agents never invent a CARGO_TARGET_DIR.

## Dependencies

- **Blocks:** [sase-zw.7](sase-zw.7.md) ◐ · ⧖ 2026-09-12

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zw.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zw.4/README.md) | [sase-zw.4](sase-zw.4.md) | 0 |
