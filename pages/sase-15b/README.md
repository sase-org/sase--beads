# Bead: sase-15b — Split The Next Ten Largest sase-core Rust Files Into \<=1500 Line Modules

[Bead Pages](../README.md) / sase-15b

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oh.r0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oh.r0.md) · **Assignee:** `sase-15b.land`
**Created:** 2026-09-21 11:31:35 EDT
**Plan:** [202609/sase\_core\_next\_ten\_big\_file\_split.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_next_ten_big_file_split.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/sase_core_next_ten_big_file_split.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 2 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_next_ten_big_file_split.md

<!-- sase:links:end -->

## Description

Each of the ten largest Rust files remaining in the sase-core repo after epic sase-14s is decomposed into a module tree whose every file is at most 1500 lines, with no behavior change, no public API change, and `just check` green after each phase.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-15b.1](sase-15b.1.md) | Split crates/sase\_core/src/bead/cli.rs | ✓ closed | medium | 2026-09-21 | 1 | 1 |
| [sase-15b.10](sase-15b.10.md) | Split crates/sase\_core/tests/notification\_store\_parity.rs | ✓ closed | medium | 2026-09-21 | 1 | 1 |
| [sase-15b.2](sase-15b.2.md) | Split crates/sase\_gateway/src/federation\_worker.rs | ✓ closed | medium | 2026-09-21 | 1 | 1 |
| [sase-15b.3](sase-15b.3.md) | Split crates/sase\_core/src/agent\_stats/run.rs | ✓ closed | medium | 2026-09-21 | 1 | 1 |
| [sase-15b.4](sase-15b.4.md) | Split crates/sase\_gateway/src/fleet\_reads.rs | ✓ closed | medium | 2026-09-21 | 1 | 1 |
| [sase-15b.5](sase-15b.5.md) | Split crates/sase\_core/src/bead/events.rs | ✓ closed | medium | 2026-09-21 | 1 | 1 |
| [sase-15b.6](sase-15b.6.md) | Split crates/sase\_core/src/tool\_run/store.rs | ✓ closed | medium | 2026-09-21 | 1 | 1 |
| [sase-15b.7](sase-15b.7.md) | Split crates/sase\_core/src/provider\_usage/tests.rs | ✓ closed | medium | 2026-09-21 | 1 | 1 |
| [sase-15b.8](sase-15b.8.md) | Split crates/sase\_core/src/editor/directive.rs | ✓ closed | medium | 2026-09-21 | 1 | 1 |
| [sase-15b.9](sase-15b.9.md) | Split crates/sase\_core/src/runner\_capacity.rs | ✓ closed | medium | 2026-09-21 | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-15b: Split The Next Ten Largest sase-core Rust Files Into &lt;=1500 Line Modules [in_progress]"]
    n1["sase-15b.1: Split crates/sase_core/src/bead/cli.rs [closed]"]
    n2["sase-15b.10: Split crates/sase_core/tests/notification_store_parity.rs [closed]"]
    n3["sase-15b.2: Split crates/sase_gateway/src/federation_worker.rs [closed]"]
    n4["sase-15b.3: Split crates/sase_core/src/agent_stats/run.rs [closed]"]
    n5["sase-15b.4: Split crates/sase_gateway/src/fleet_reads.rs [closed]"]
    n6["sase-15b.5: Split crates/sase_core/src/bead/events.rs [closed]"]
    n7["sase-15b.6: Split crates/sase_core/src/tool_run/store.rs [closed]"]
    n8["sase-15b.7: Split crates/sase_core/src/provider_usage/tests.rs [closed]"]
    n9["sase-15b.8: Split crates/sase_core/src/editor/directive.rs [closed]"]
    n10["sase-15b.9: Split crates/sase_core/src/runner_capacity.rs [closed]"]
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
    n1 -.-> n3
    n3 -.-> n4
    n4 -.-> n5
    n5 -.-> n6
    n6 -.-> n7
    n7 -.-> n8
    n8 -.-> n9
    n9 -.-> n10
    n10 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-15b.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.1/README.md) | [sase-15b.1](sase-15b.1.md) | 1 |
| [bbugyi200.athena.sase-15b.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.10/README.md) | [sase-15b.10](sase-15b.10.md) | 1 |
| [bbugyi200.athena.sase-15b.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.2/README.md) | [sase-15b.2](sase-15b.2.md) | 1 |
| [bbugyi200.athena.sase-15b.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.3/README.md) | [sase-15b.3](sase-15b.3.md) | 1 |
| [bbugyi200.athena.sase-15b.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.4/README.md) | [sase-15b.4](sase-15b.4.md) | 1 |
| [bbugyi200.athena.sase-15b.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.5/README.md) | [sase-15b.5](sase-15b.5.md) | 1 |
| [bbugyi200.athena.sase-15b.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.6/README.md) | [sase-15b.6](sase-15b.6.md) | 1 |
| [bbugyi200.athena.sase-15b.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.7/README.md) | [sase-15b.7](sase-15b.7.md) | 1 |
| [bbugyi200.athena.sase-15b.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.8/README.md) | [sase-15b.8](sase-15b.8.md) | 1 |
| [bbugyi200.athena.sase-15b.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.9/README.md) | [sase-15b.9](sase-15b.9.md) | 1 |
| [bbugyi200.athena.sase-15b.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.land/README.md) | [sase-15b](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@61dc4e1`](https://github.com/sase-org/sase-core/commit/61dc4e19713189e8e9d0a2e3aeedafcf16d584ad) | refactor(bead): split bead cli.rs into bead/cli module tree | [sase-15b.1](sase-15b.1.md) | 2026-09-21 13:46:20 EDT |
| sase-core | [`sase-core@b5cea78`](https://github.com/sase-org/sase-core/commit/b5cea78ea99fd4f5210aabcf11036c56f02b293b) | refactor(gateway): split federation\_worker.rs into federation\_worker/ module tree | [sase-15b.2](sase-15b.2.md) | 2026-09-21 14:16:57 EDT |
| sase-core | [`sase-core@006dd16`](https://github.com/sase-org/sase-core/commit/006dd162cd11a0afbc0c70d2b604bd41f8ffbc64) | refactor(agent\_stats): split run.rs into run/ module tree | [sase-15b.3](sase-15b.3.md) | 2026-09-21 14:50:10 EDT |
| sase-core | [`sase-core@e93e248`](https://github.com/sase-org/sase-core/commit/e93e24879f7be9f04e0e29377735676f738f55b2) | refactor(sase-gateway): split fleet\_reads into module tree | [sase-15b.4](sase-15b.4.md) | 2026-09-21 15:25:36 EDT |
| sase-core | [`sase-core@ad732d6`](https://github.com/sase-org/sase-core/commit/ad732d67480bea95cc5a64428988ffb522731e81) | refactor(sase-core): split bead events into wire, import, reduction, merge modules | [sase-15b.5](sase-15b.5.md) | 2026-09-21 15:55:32 EDT |
| sase-core | [`sase-core@b7af6b7`](https://github.com/sase-org/sase-core/commit/b7af6b7ce58a0888253e1f8223f2e502512d33bb) | refactor(sase-core): split tool\_run store into connection, lifecycle, query, retention modules | [sase-15b.6](sase-15b.6.md) | 2026-09-21 16:21:13 EDT |
| sase-core | [`sase-core@71b05bb`](https://github.com/sase-org/sase-core/commit/71b05bbce8b71e55fa6201fd0d4e5e5e0991a171) | refactor(sase-core): split provider\_usage tests into tests/ directory | [sase-15b.7](sase-15b.7.md) | 2026-09-21 16:56:29 EDT |
| sase-core | [`sase-core@59327d6`](https://github.com/sase-org/sase-core/commit/59327d62c18b61c8680d367e69ab58c6f1c296f9) | refactor(sase-core): split editor directive into metadata, contract, candidate, context modules | [sase-15b.8](sase-15b.8.md) | 2026-09-21 17:21:30 EDT |
| sase-core | [`sase-core@f54b2ba`](https://github.com/sase-org/sase-core/commit/f54b2ba4cb7c38739f0a9c5c202ca1a4077de9d4) | refactor(sase-core): split runner\_capacity into module tree | [sase-15b.9](sase-15b.9.md) | 2026-09-21 17:52:24 EDT |
| sase-core | [`sase-core@8886406`](https://github.com/sase-org/sase-core/commit/88864065127efa138b71c3e778b60916a5f81b17) | refactor(sase-core): split notification\_store\_parity test into behavior-area modules | [sase-15b.10](sase-15b.10.md) | 2026-09-21 18:12:37 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.24.cld][1] | research sase-core agent maintainability | 2 |
| read-by | [agent:sase-15b.2][2] | epic symbols check | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.research.24.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-15b.2/README.md

<!-- sase:referenced-by:end -->
