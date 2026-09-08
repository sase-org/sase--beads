# Bead: sase-xe.16.2 — Ratchet the core pin and dependency floor past the new surface

[Bead Pages](../README.md) / [sase-xe.16](sase-xe.16.md) / sase-xe.16.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08c.md) · **Assignee:** `sase-xe.16.2` · **Size:** small
**Created:** 2026-09-08 10:21:33 EDT
**Plan:** [202609/remote\_dispatch\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_completion.md)

## Description

core-pin-and-floor: in the sase repo, once sase-core's remote HEAD contains core-fleet-surface, run `just ratchet-core-revision` to advance sase-core-revision.txt (this also finally ratchets past the sase-xe flag-removal commit that the sase-y9 five-node directive skew is waiting on), bump the `sase-core-rs` floor in pyproject.toml to the release that carries the new surface once it is published, and keep `tools/check_sase_core_rs_bindings` / `tools/validate_sase_core_rs` green. Wait for the release with /sase_monitor; if the release-plz release PR needs a human merge, raise it with /sase_questions instead of guessing.

## Dependencies

- **Depends on:** [sase-xe.16.1](sase-xe.16.1.md) ◐ · ⧖ 2026-09-08
- **Blocks:** [sase-xe.16.10](sase-xe.16.10.md) ◐ · ⧖ 2026-09-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xe.16.2/README.md) | [sase-xe.16.2](sase-xe.16.2.md) | 0 |
