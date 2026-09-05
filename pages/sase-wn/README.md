# Bead: sase-wn — Idle CPU diet: stop sase from burning ~4 cores at rest

[Bead Pages](../README.md) / sase-wn

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.o.f0` · **Assignee:** `sase-wn.land`
**Created:** 2026-09-04 12:10:57 EDT
**Plan:** [202609/sase\_idle\_cpu\_diet.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_idle_cpu_diet.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/sase_idle_cpu_diet.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/sase_idle_cpu_diet.md

<!-- sase:links:end -->

## Description

An idle sase host (ace open, lumberjacks running, no agent work) drops from roughly four sustained cores of sase CPU to well under half a core — by eliminating per-chop interpreter boot waste, skipping chop subprocess spawns when their inputs are provably unchanged, replacing ace's unconditional full-disk refresh with cheap per-surface change tokens, caching immutable axe status reads, and reusing one sase-core release build across workspaces — all without changing chop cadence, subprocess isolation, timeout semantics, or user-visible TUI freshness.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-wn.1](sase-wn.1.md) | Slim chop subprocess imports | ✓ closed | medium | 2026-09-04 | 1 | 1 |
| [sase-wn.10](sase-wn.10.md) | Perf counters, budgets, and regression guardrails | ✓ closed | medium | 2026-09-04 | 1 | 1 |
| [sase-wn.2](sase-wn.2.md) | Filesystem change-token trigger provider (sase-core) | ✓ closed | medium | 2026-09-04 | 1 | 2 |
| [sase-wn.3](sase-wn.3.md) | Wire pre-spawn guards into shipped chop defaults | ✓ closed | medium | 2026-09-04 | 1 | 1 |
| [sase-wn.4](sase-wn.4.md) | Make wait\_checks and bead\_claim\_checks incremental | ✓ closed | medium | 2026-09-04 | 0 | 1 |
| [sase-wn.5](sase-wn.5.md) | Per-surface change tokens for ace auto-refresh | ✓ closed | large | 2026-09-04 | 1 | 1 |
| [sase-wn.6](sase-wn.6.md) | Cache immutable axe status reads in ace | ✓ closed | medium | 2026-09-04 | 1 | 1 |
| [sase-wn.7](sase-wn.7.md) | Stop multi-second idle re-renders of the prompt panel | ✓ closed | medium | 2026-09-04 | 1 | 1 |
| [sase-wn.8](sase-wn.8.md) | Small ace I/O fixes (agents-sync reads, bead N+1) | ✓ closed | small | 2026-09-04 | 1 | 1 |
| [sase-wn.9](sase-wn.9.md) | Reuse sase-core release builds across workspaces | ✓ closed | medium | 2026-09-04 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-wn: Idle CPU diet: stop sase from burning ~4 cores at rest [in_progress]"]
    n1["sase-wn.1: Slim chop subprocess imports [closed]"]
    n2["sase-wn.10: Perf counters, budgets, and regression guardrails [closed]"]
    n3["sase-wn.2: Filesystem change-token trigger provider (sase-core) [closed]"]
    n4["sase-wn.3: Wire pre-spawn guards into shipped chop defaults [closed]"]
    n5["sase-wn.4: Make wait_checks and bead_claim_checks incremental [closed]"]
    n6["sase-wn.5: Per-surface change tokens for ace auto-refresh [closed]"]
    n7["sase-wn.6: Cache immutable axe status reads in ace [closed]"]
    n8["sase-wn.7: Stop multi-second idle re-renders of the prompt panel [closed]"]
    n9["sase-wn.8: Small ace I/O fixes (agents-sync reads, bead N+1) [closed]"]
    n10["sase-wn.9: Reuse sase-core release builds across workspaces [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n0 --> n10
    n1 -.-> n2
    n3 -.-> n4
    n4 -.-> n2
    n6 -.-> n2
    n6 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-wn.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.1/README.md) | [sase-wn.1](sase-wn.1.md) | 1 |
| [bbugyi200.apollo.sase-wn.10](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-wn.10.md) | [sase-wn.10](sase-wn.10.md) | 1 |
| [bbugyi200.apollo.sase-wn.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.2/README.md) | [sase-wn.2](sase-wn.2.md) | 2 |
| [bbugyi200.apollo.sase-wn.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.3/README.md) | [sase-wn.3](sase-wn.3.md) | 1 |
| [bbugyi200.apollo.sase-wn.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.sase-wn.5.md) | [sase-wn.5](sase-wn.5.md) | 1 |
| [bbugyi200.apollo.sase-wn.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.6/README.md) | [sase-wn.6](sase-wn.6.md) | 1 |
| [bbugyi200.apollo.sase-wn.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.7/README.md) | [sase-wn.7](sase-wn.7.md) | 1 |
| [bbugyi200.apollo.sase-wn.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.8/README.md) | [sase-wn.8](sase-wn.8.md) | 1 |
| [bbugyi200.apollo.sase-wn.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.9/README.md) | [sase-wn.9](sase-wn.9.md) | 1 |
| [bbugyi200.apollo.sase-wn.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-wn.land/README.md) | [sase-wn](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`3a48a4c`](https://github.com/sase-org/sase/commit/3a48a4c65b10d7a5e1aa777669fa258b2d5aa2d6) | feat(axe): add pluggable chop trigger provider policy with fs support | [sase-wn.2](sase-wn.2.md) | 2026-09-04 12:50:58 EDT |
| sase-core | [`sase-core@31abd5f`](https://github.com/sase-org/sase-core/commit/31abd5f0b65fe2586b12fc3456e3bf29d4f49da1) | feat(axe\_chop): add trigger provider config, decision, and wire types | [sase-wn.2](sase-wn.2.md) | 2026-09-04 13:20:44 EDT |
| sase | [`4924c8b`](https://github.com/sase-org/sase/commit/4924c8b9b9027c771441361904d4ddc07775dfb9) | feat: Make wait\_checks and bead\_claim\_checks incremental (sase-wn.4) | [sase-wn.4](sase-wn.4.md) | 2026-09-04 14:53:05 EDT |
| sase | [`c0ae9d2`](https://github.com/sase-org/sase/commit/c0ae9d2d05901cfd9a96f36fdf8240ae2804f1bd) | perf(ace): buffer cat-file reads and batch wait-bead status lookups | [sase-wn.8](sase-wn.8.md) | 2026-09-04 15:40:57 EDT |
| sase | [`da95c82`](https://github.com/sase-org/sase/commit/da95c82480b8ab258478fdd5eacdaf49abfd519c) | feat: cache sase-core release wheels | [sase-wn.9](sase-wn.9.md) | 2026-09-04 17:33:47 EDT |
| sase | [`c0b741c`](https://github.com/sase-org/sase/commit/c0b741c9363e58abadf8732ef7bd6fa35521f212) | perf(chops): defer heavy runner imports to cut chop import budget | [sase-wn.1](sase-wn.1.md) | 2026-09-04 17:56:43 EDT |
| sase | [`969c22b`](https://github.com/sase-org/sase/commit/969c22ba06edd575ff26629f2c11a6547ab3b71b) | feat(ace): cache idle prompt-panel renders of unchanged documents | [sase-wn.7](sase-wn.7.md) | 2026-09-04 19:06:31 EDT |
| sase | [`2eb1335`](https://github.com/sase-org/sase/commit/2eb13350f991a84b340f4d6619334b9311bd7f9c) | feat(ace): gate auto-refresh on per-surface change tokens | [sase-wn.5](sase-wn.5.md) | 2026-09-04 20:53:28 EDT |
| sase | [`0927b10`](https://github.com/sase-org/sase/commit/0927b10928b344372127ac956226855f6ccb8b44) | perf(ace): cache immutable axe status reads across ticks | [sase-wn.6](sase-wn.6.md) | 2026-09-04 22:30:20 EDT |
| sase | [`ad5bcc9`](https://github.com/sase-org/sase/commit/ad5bcc914b84c5ef3696bf43805038ba354e1800) | feat(ace): wire fs change-token guards into shipped hooks/waits chops | [sase-wn.3](sase-wn.3.md) | 2026-09-05 06:51:02 EDT |
| sase | [`9ed0f11`](https://github.com/sase-org/sase/commit/9ed0f11b7c21c5da288833b44bfeb85ca12f16fc) | feat(axe): add idle-host perf counters, budgets, and status overlay | [sase-wn.10](sase-wn.10.md) | 2026-09-05 17:36:31 EDT |
