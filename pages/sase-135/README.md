# Bead: sase-135 — Named tools and the foreground ToolRun ledger

[Bead Pages](../README.md) / sase-135

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0nm](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0nm.md) · **Assignee:** `sase-135.land`
**Created:** 2026-09-18 22:19:17 EDT
**Plan:** [202609/tool\_e1\_named\_tools.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e1_named_tools.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/tool_e1_named_tools.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/tool_e1_named_tools.md

<!-- sase:links:end -->

## Description

Deliver project-owned named commands and a Rust-owned, machine-local ToolRun ledger through sase tool list/run/runs/show, preserving command behavior while recording stages, fingerprints, and host load, with bounded retention, adoption guidance, and reproducible black-box acceptance evidence.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-135.1](sase-135.1.md) | Establish the versioned ToolRun store and bindings | ✓ closed | medium | 2026-09-18 | 1 | 2 |
| [sase-135.2](sase-135.2.md) | Add the project-owned catalog and tool list command | ◐ in_progress | medium | 2026-09-18 | 1 | 0 |
| [sase-135.3](sase-135.3.md) | Execute and inspect foreground runs reliably | ◐ in_progress | medium | 2026-09-18 | 1 | 0 |
| [sase-135.4](sase-135.4.md) | Record run\_silent stages and render the timeline | ◐ in_progress | medium | 2026-09-18 | 1 | 0 |
| [sase-135.5](sase-135.5.md) | Capture fingerprints, host samples, and recording metrics | ◐ in_progress | medium | 2026-09-18 | 1 | 0 |
| [sase-135.6](sase-135.6.md) | Teach the tool workflow and measure its adoption | ◐ in_progress | medium | 2026-09-18 | 1 | 0 |
| [sase-135.7](sase-135.7.md) | Prove the combined product and publish rerunnable evidence | ◐ in_progress | medium | 2026-09-18 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-135: Named tools and the foreground ToolRun ledger [in_progress]"]
    n1["sase-135.1: Establish the versioned ToolRun store and bindings [closed]"]
    n2["sase-135.2: Add the project-owned catalog and tool list command [in_progress]"]
    n3["sase-135.3: Execute and inspect foreground runs reliably [in_progress]"]
    n4["sase-135.4: Record run_silent stages and render the timeline [in_progress]"]
    n5["sase-135.5: Capture fingerprints, host samples, and recording metrics [in_progress]"]
    n6["sase-135.6: Teach the tool workflow and measure its adoption [in_progress]"]
    n7["sase-135.7: Prove the combined product and publish rerunnable evidence [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n1 -.-> n2
    n2 -.-> n3
    n3 -.-> n4
    n4 -.-> n5
    n5 -.-> n6
    n6 -.-> n7
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-135.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-135.1.md) | [sase-135.1](sase-135.1.md) | 2 |
| [bbugyi200.athena.sase-135.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-135.2/README.md) | [sase-135.2](sase-135.2.md) | 0 |
| [bbugyi200.athena.sase-135.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-135.3/README.md) | [sase-135.3](sase-135.3.md) | 0 |
| [bbugyi200.athena.sase-135.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-135.4/README.md) | [sase-135.4](sase-135.4.md) | 0 |
| [bbugyi200.athena.sase-135.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-135.5/README.md) | [sase-135.5](sase-135.5.md) | 0 |
| [bbugyi200.athena.sase-135.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-135.6/README.md) | [sase-135.6](sase-135.6.md) | 0 |
| [bbugyi200.athena.sase-135.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-135.7/README.md) | [sase-135.7](sase-135.7.md) | 0 |
| [bbugyi200.athena.sase-135.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-135.land/README.md) | [sase-135](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9cfa200`](https://github.com/sase-org/sase/commit/9cfa20067519122b6737890dff68a883d43e49d2) | feat(tool-run): land V1 ToolRun bindings, disk owner, and smokes | [sase-135.1](sase-135.1.md) | 2026-09-19 04:46:06 EDT |
| sase-core | [`sase-core@44b82c3`](https://github.com/sase-org/sase-core/commit/44b82c3e392bb4642fbb909a2d656b8e94d2cadd) | feat(tool-run): add ToolRun store, PyO3 bindings, and reserved tool kind | [sase-135.1](sase-135.1.md) | 2026-09-19 04:56:12 EDT |
