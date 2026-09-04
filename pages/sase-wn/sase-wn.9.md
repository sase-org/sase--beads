# Bead: sase-wn.9 — Reuse sase-core release builds across workspaces

[Bead Pages](../README.md) / [sase-wn](README.md) / sase-wn.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.o.f0` · **Assignee:** `sase-wn.9` · **Size:** medium
**Created:** 2026-09-04 12:11:15 EDT
**Plan:** [202609/sase\_idle\_cpu\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_idle_cpu_diet.md)

## Description

core-build-cache: add a host-level sase_core_rs wheel cache keyed by sase-core commit, toolchain, and ABI so ephemeral workspaces install a cached wheel instead of each running a multi-core-minute maturin release build; cache miss or dirty checkout falls back to today's build path.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wn.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.9/README.md) | [sase-wn.9](sase-wn.9.md) | 0 |
