# Bead: sase-zf — Unify the Agents tab query language with the Artifacts Agent pane

[Bead Pages](../README.md) / sase-zf

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0iy](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0iy.md) · **Assignee:** `sase-zf.land`
**Created:** 2026-09-10 18:01:45 EDT
**Plan:** [202609/agents\_query\_unification.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_query_unification.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/agents_query_unification.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/agents_query_unification.md

<!-- sase:links:end -->

## Description

The top-level Agents tab filters with the same boolean query-profile dialect, Rust-backed evaluation, and FilterBar editing chrome as the Artifacts Agent pane, with zero idle screen-space cost and no measurable performance regression.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-zf.1](sase-zf.1.md) | Shared agents-live query profile and row adapter | ✓ closed | medium | 2026-09-10 | 1 | 2 |
| [sase-zf.2](sase-zf.2.md) | Rust-backed committed-query engine behind a sunset flag | ✓ closed | medium | 2026-09-10 | 1 | 1 |
| [sase-zf.3](sase-zf.3.md) | Load-path pushdown parity and secondary query consumers | ✓ closed | medium | 2026-09-10 | 1 | 1 |
| [sase-zf.4](sase-zf.4.md) | Auto-hiding FilterBar chrome on the Agents tab | ✓ closed | medium | 2026-09-10 | 1 | 1 |
| [sase-zf.5](sase-zf.5.md) | Documentation rewrite and verification sweep | ✓ closed | small | 2026-09-10 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-zf: Unify the Agents tab query language with the Artifacts Agent pane [in_progress]"]
    n1["sase-zf.1: Shared agents-live query profile and row adapter [closed]"]
    n2["sase-zf.2: Rust-backed committed-query engine behind a sunset flag [closed]"]
    n3["sase-zf.3: Load-path pushdown parity and secondary query consumers [closed]"]
    n4["sase-zf.4: Auto-hiding FilterBar chrome on the Agents tab [closed]"]
    n5["sase-zf.5: Documentation rewrite and verification sweep [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n1 -.-> n2
    n2 -.-> n3
    n2 -.-> n4
    n3 -.-> n4
    n4 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zf.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zf.1/README.md) | [sase-zf.1](sase-zf.1.md) | 2 |
| [bbugyi200.athena.sase-zf.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zf.2/README.md) | [sase-zf.2](sase-zf.2.md) | 1 |
| [bbugyi200.athena.sase-zf.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zf.3/README.md) | [sase-zf.3](sase-zf.3.md) | 1 |
| [bbugyi200.athena.sase-zf.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zf.4/README.md) | [sase-zf.4](sase-zf.4.md) | 1 |
| [bbugyi200.athena.sase-zf.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zf.5/README.md) | [sase-zf.5](sase-zf.5.md) | 1 |
| [bbugyi200.athena.sase-zf.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zf.land/README.md) | [sase-zf](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`bfcdc04`](https://github.com/sase-org/sase/commit/bfcdc0416288ba8d9175177ecbdadaf6a3e64c9e) | feat(query): add agents-live profile adapter | [sase-zf.1](sase-zf.1.md) | 2026-09-10 18:56:37 EDT |
| sase-core | [`sase-core@7d6dfcf`](https://github.com/sase-org/sase-core/commit/7d6dfcfa96ec50003df79fc0942726a51bc1db52) | fix(query): quote canonical property values | [sase-zf.1](sase-zf.1.md) | 2026-09-10 18:59:47 EDT |
| sase | [`699d2ad`](https://github.com/sase-org/sase/commit/699d2adf7a8ab928c0bcfa57dedfb54357f9189c) | feat(agents-tab): add Rust-backed committed-query engine behind sunset flag | [sase-zf.2](sase-zf.2.md) | 2026-09-10 20:02:31 EDT |
| sase | [`e62e96f`](https://github.com/sase-org/sase/commit/e62e96f5ff917f5837051f2a192f842f453ce18d) | feat(agents): push down live query filters | [sase-zf.3](sase-zf.3.md) | 2026-09-10 20:45:16 EDT |
| sase | [`6278e02`](https://github.com/sase-org/sase/commit/6278e02c446a430671c96273b034fd0ada67c157) | feat(agents-tab): add auto-hiding FilterBar chrome (sase-zf.4) | [sase-zf.4](sase-zf.4.md) | 2026-09-10 22:04:56 EDT |
| sase | [`a53f4d0`](https://github.com/sase-org/sase/commit/a53f4d04e5fa8e45452a3e293d1edeee6188fc23) | docs(ace): document unified agents query syntax | [sase-zf.5](sase-zf.5.md) | 2026-09-10 22:28:25 EDT |
