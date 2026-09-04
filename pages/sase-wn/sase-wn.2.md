# Bead: sase-wn.2 — Filesystem change-token trigger provider (sase-core)

[Bead Pages](../README.md) / [sase-wn](README.md) / sase-wn.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.o.f0` · **Assignee:** `sase-wn.2` · **Size:** medium
**Created:** 2026-09-04 12:11:01 EDT
**Plan:** [202609/sase\_idle\_cpu\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_idle_cpu_diet.md)

## Description

chop-trigger-provider: add an fs change-token trigger provider to the sase-core axe_chop preflight engine (paths -> cheap state token, fire on change, fail-open, max_quiet fallback), with Rust tests, binding surface, and Python plumbing; no shipped chop uses it yet.

## Dependencies

- **Blocks:** [sase-wn.3](sase-wn.3.md) ◐ · ⧖ 2026-09-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wn.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.2/README.md) | [sase-wn.2](sase-wn.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3a48a4c`](https://github.com/sase-org/sase/commit/3a48a4c65b10d7a5e1aa777669fa258b2d5aa2d6) | feat(axe): add pluggable chop trigger provider policy with fs support | [sase-wn.2](sase-wn.2.md) | 2026-09-04 12:50:58 EDT |
