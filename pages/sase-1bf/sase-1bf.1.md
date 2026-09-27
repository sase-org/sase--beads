# Bead: sase-1bf.1 — Managed temp root registry the reaper follows

[Bead Pages](../README.md) / [sase-1bf](README.md) / sase-1bf.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.1d` · **Assignee:** `sase-1bf.1` · **Size:** medium
**Created:** 2026-09-27 14:23:30 EDT
**Plan:** [202609/bounded\_agent\_scratch.md](https://github.com/sase-org/sase--plans/blob/main/202609/bounded_agent_scratch.md)

## Description

root-registry: every root `get_sase_managed_tmpdir()` writes into is recorded in a Rust-owned registry under SASE_HOME, and every managed-tmp reaper entry point reaps all registered roots instead of only the root its own environment resolves.

## Dependencies

- **Blocks:** [sase-1bf.3](sase-1bf.3.md) ◐ · ⧖ 2026-09-27
- **Blocks:** [sase-1bf.4](sase-1bf.4.md) ◐ · ⧖ 2026-09-27
- **Blocks:** [sase-1bf.6](sase-1bf.6.md) ◐ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bf.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bf.1/README.md) | [sase-1bf.1](sase-1bf.1.md) | 0 |
