# Bead: sase-14s — Split The Ten Largest sase-core Rust Files Into \<=1500 Line Modules

[Bead Pages](../README.md) / sase-14s

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oh.md) · **Assignee:** `sase-14s.land`
**Created:** 2026-09-20 19:06:06 EDT
**Plan:** [202609/sase\_core\_big\_file\_split.md](https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_big_file_split.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/sase_core_big_file_split.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/sase_core_big_file_split.md

<!-- sase:links:end -->

## Description

Each of the ten largest Rust files in the sase-core repo is decomposed into a module tree whose every file is at most 1500 lines, with no behavior change, no public API change, and `just check` green after each phase.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-14s.1](sase-14s.1.md) | Split crates/sase\_core\_py/src/lib.rs | ✓ closed | medium | 2026-09-20 | 1 | 1 |
| [sase-14s.10](sase-14s.10.md) | Split crates/sase\_gateway/src/sudo\_runner.rs | ◐ in_progress | medium | 2026-09-20 | 1 | 0 |
| [sase-14s.2](sase-14s.2.md) | Split crates/sase\_core/src/agent\_scan/index.rs | ✓ closed | medium | 2026-09-20 | 1 | 1 |
| [sase-14s.3](sase-14s.3.md) | Split crates/sase\_core/src/bead/mutation.rs | ◐ in_progress | medium | 2026-09-20 | 1 | 0 |
| [sase-14s.4](sase-14s.4.md) | Split crates/sase\_core/src/fleet\_contract.rs | ◐ in_progress | medium | 2026-09-20 | 1 | 0 |
| [sase-14s.5](sase-14s.5.md) | Split crates/sase\_gateway/src/routes.rs | ◐ in_progress | medium | 2026-09-20 | 1 | 0 |
| [sase-14s.6](sase-14s.6.md) | Split crates/sase\_xprompt\_lsp/src/server.rs | ◐ in_progress | medium | 2026-09-20 | 1 | 0 |
| [sase-14s.7](sase-14s.7.md) | Split crates/sase\_core/src/agent\_launch/mod.rs | ◐ in_progress | medium | 2026-09-20 | 1 | 0 |
| [sase-14s.8](sase-14s.8.md) | Split crates/sase\_core/src/editor/completion.rs | ◐ in_progress | medium | 2026-09-20 | 1 | 0 |
| [sase-14s.9](sase-14s.9.md) | Split crates/sase\_core/src/xprompt\_catalog.rs | ◐ in_progress | medium | 2026-09-20 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-14s: Split The Ten Largest sase-core Rust Files Into &lt;=1500 Line Modules [in_progress]"]
    n1["sase-14s.1: Split crates/sase_core_py/src/lib.rs [closed]"]
    n2["sase-14s.10: Split crates/sase_gateway/src/sudo_runner.rs [in_progress]"]
    n3["sase-14s.2: Split crates/sase_core/src/agent_scan/index.rs [closed]"]
    n4["sase-14s.3: Split crates/sase_core/src/bead/mutation.rs [in_progress]"]
    n5["sase-14s.4: Split crates/sase_core/src/fleet_contract.rs [in_progress]"]
    n6["sase-14s.5: Split crates/sase_gateway/src/routes.rs [in_progress]"]
    n7["sase-14s.6: Split crates/sase_xprompt_lsp/src/server.rs [in_progress]"]
    n8["sase-14s.7: Split crates/sase_core/src/agent_launch/mod.rs [in_progress]"]
    n9["sase-14s.8: Split crates/sase_core/src/editor/completion.rs [in_progress]"]
    n10["sase-14s.9: Split crates/sase_core/src/xprompt_catalog.rs [in_progress]"]
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
| [bbugyi200.athena.sase-14s.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14s.1/README.md) | [sase-14s.1](sase-14s.1.md) | 1 |
| [bbugyi200.athena.sase-14s.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14s.10/README.md) | [sase-14s.10](sase-14s.10.md) | 0 |
| [bbugyi200.athena.sase-14s.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14s.2/README.md) | [sase-14s.2](sase-14s.2.md) | 1 |
| [bbugyi200.athena.sase-14s.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14s.3/README.md) | [sase-14s.3](sase-14s.3.md) | 0 |
| [bbugyi200.athena.sase-14s.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14s.4/README.md) | [sase-14s.4](sase-14s.4.md) | 0 |
| [bbugyi200.athena.sase-14s.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14s.5/README.md) | [sase-14s.5](sase-14s.5.md) | 0 |
| [bbugyi200.athena.sase-14s.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14s.6/README.md) | [sase-14s.6](sase-14s.6.md) | 0 |
| [bbugyi200.athena.sase-14s.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14s.7/README.md) | [sase-14s.7](sase-14s.7.md) | 0 |
| [bbugyi200.athena.sase-14s.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14s.8/README.md) | [sase-14s.8](sase-14s.8.md) | 0 |
| [bbugyi200.athena.sase-14s.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14s.9/README.md) | [sase-14s.9](sase-14s.9.md) | 0 |
| [bbugyi200.athena.sase-14s.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14s.land/README.md) | [sase-14s](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@03036af`](https://github.com/sase-org/sase-core/commit/03036afdbf9b510550d3c60b6e08357ce939c992) | refactor(sase\_core\_py): split 35kloc lib.rs into domain module tree | [sase-14s.1](sase-14s.1.md) | 2026-09-20 20:27:04 EDT |
| sase-core | [`sase-core@601d4e7`](https://github.com/sase-org/sase-core/commit/601d4e73c4fe467cba9f0acbae9e688999e46371) | refactor(agent\_scan): split 13kloc index.rs into domain module tree | [sase-14s.2](sase-14s.2.md) | 2026-09-20 21:19:29 EDT |
