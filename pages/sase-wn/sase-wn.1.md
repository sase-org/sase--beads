# Bead: sase-wn.1 — Slim chop subprocess imports

[Bead Pages](../README.md) / [sase-wn](README.md) / sase-wn.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.o.f0` · **Assignee:** `sase-wn.1` · **Size:** medium
**Created:** 2026-09-04 12:10:59 EDT
**Plan:** [202609/sase\_idle\_cpu\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_idle_cpu_diet.md)

## Description

chop-import-slim: cut the ~0.6s/1,251-module import cost every sase_chop_* subprocess pays before doing any work, by making sase.axe lazy, trimming the chops SDK import chain, and adding an import-budget regression test; no behavior change.

## Dependencies

- **Blocks:** [sase-wn.10](sase-wn.10.md) ◐ · ⧖ 2026-09-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wn.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.1/README.md) | [sase-wn.1](sase-wn.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c0b741c`](https://github.com/sase-org/sase/commit/c0b741c9363e58abadf8732ef7bd6fa35521f212) | perf(chops): defer heavy runner imports to cut chop import budget | [sase-wn.1](sase-wn.1.md) | 2026-09-04 17:56:43 EDT |
