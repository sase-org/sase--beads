# Bead: sase-i9.2 — Build the Rust core and LSP in one feature-unified cargo invocation

[Bead Pages](../README.md) / [sase-i9](README.md) / sase-i9.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wj](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wj/README.md) · **Assignee:** `sase-i9.2` · **Size:** medium
**Created:** 2026-08-09 10:10:48 EDT
**Plan:** [202608/fast\_dev\_update.md](https://github.com/sase-org/sase--plans/blob/main/202608/fast_dev_update.md)

## Description

unified-build: collapse the two separate cargo/maturin reconcile steps into a single feature-unified build so sase_core and its shared dependencies compile once per update instead of twice, and so the two builds stop invalidating each other's cached units.

## Dependencies

- **Depends on:** [sase-i9.1](sase-i9.1.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-i9.3](sase-i9.3.md) ◐ · ⧖ 2026-08-09
- **Blocks:** [sase-i9.4](sase-i9.4.md) ◐ · ⧖ 2026-08-09
- **Blocks:** [sase-i9.5](sase-i9.5.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i9.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i9.2/README.md) | [sase-i9.2](sase-i9.2.md) | 0 |
