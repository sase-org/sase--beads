# Bead: sase-157 — Make sase-core correct and green on macOS

[Bead Pages](../README.md) / sase-157

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oj.md) · **Assignee:** `sase-157.land`
**Created:** 2026-09-21 06:25:42 EDT
**Plan:** [202609/macos\_portability.md](https://github.com/sase-org/sase--plans/blob/main/202609/macos_portability.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/macos_portability.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/macos_portability.md

<!-- sase:links:end -->

## Description

The managed-tmp reap guard refuses broad roots on every platform and no test can perform a live reap, every sase-core workspace test passes on macOS, and a required macOS CI leg keeps it that way.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-157.1](sase-157.1.md) | Fix the managed-tmp reap guard and disarm its test | ✓ closed | small | 2026-09-21 | 1 | 1 |
| [sase-157.2](sase-157.2.md) | Let the verification gate run a filtered suite | ◐ in_progress | xsmall | 2026-09-21 | 1 | 0 |
| [sase-157.3](sase-157.3.md) | Add an advisory macOS CI leg | ◐ in_progress | small | 2026-09-21 | 1 | 0 |
| [sase-157.4](sase-157.4.md) | Gate the procfs process-identity token to Linux | ◐ in_progress | medium | 2026-09-21 | 1 | 0 |
| [sase-157.5](sase-157.5.md) | Fix the detached handoff started-path mismatch | ◐ in_progress | medium | 2026-09-21 | 1 | 0 |
| [sase-157.6](sase-157.6.md) | Decide how attachment validation treats symlinked ancestors | ◐ in_progress | medium | 2026-09-21 | 1 | 0 |
| [sase-157.7](sase-157.7.md) | Reconcile canonicalized paths across sase\_core and the bindings | ◐ in_progress | medium | 2026-09-21 | 1 | 0 |
| [sase-157.8](sase-157.8.md) | Make LSP definition URIs agree with their expectations | ◐ in_progress | small | 2026-09-21 | 1 | 0 |
| [sase-157.9](sase-157.9.md) | Make the macOS leg required and document the loop | ◐ in_progress | small | 2026-09-21 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-157: Make sase-core correct and green on macOS [in_progress]"]
    n1["sase-157.1: Fix the managed-tmp reap guard and disarm its test [closed]"]
    n2["sase-157.2: Let the verification gate run a filtered suite [in_progress]"]
    n3["sase-157.3: Add an advisory macOS CI leg [in_progress]"]
    n4["sase-157.4: Gate the procfs process-identity token to Linux [in_progress]"]
    n5["sase-157.5: Fix the detached handoff started-path mismatch [in_progress]"]
    n6["sase-157.6: Decide how attachment validation treats symlinked ancestors [in_progress]"]
    n7["sase-157.7: Reconcile canonicalized paths across sase_core and the bindings [in_progress]"]
    n8["sase-157.8: Make LSP definition URIs agree with their expectations [in_progress]"]
    n9["sase-157.9: Make the macOS leg required and document the loop [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n0 --> n9
    n1 -.-> n2
    n2 -.-> n3
    n3 -.-> n4
    n3 -.-> n6
    n3 -.-> n7
    n3 -.-> n8
    n4 -.-> n5
    n5 -.-> n9
    n6 -.-> n9
    n7 -.-> n9
    n8 -.-> n9
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-157.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.1/README.md) | [sase-157.1](sase-157.1.md) | 1 |
| [bbugyi200.athena.sase-157.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.2/README.md) | [sase-157.2](sase-157.2.md) | 0 |
| [bbugyi200.athena.sase-157.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.3/README.md) | [sase-157.3](sase-157.3.md) | 0 |
| [bbugyi200.athena.sase-157.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.4/README.md) | [sase-157.4](sase-157.4.md) | 0 |
| [bbugyi200.athena.sase-157.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.5/README.md) | [sase-157.5](sase-157.5.md) | 0 |
| [bbugyi200.athena.sase-157.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.6/README.md) | [sase-157.6](sase-157.6.md) | 0 |
| [bbugyi200.athena.sase-157.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.7/README.md) | [sase-157.7](sase-157.7.md) | 0 |
| [bbugyi200.athena.sase-157.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.8/README.md) | [sase-157.8](sase-157.8.md) | 0 |
| [bbugyi200.athena.sase-157.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.9/README.md) | [sase-157.9](sase-157.9.md) | 0 |
| [bbugyi200.athena.sase-157.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.land/README.md) | [sase-157](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@60782f2`](https://github.com/sase-org/sase-core/commit/60782f2dfc2c82ceeb59394d8ac46d8a096317c0) | fix(sase-core): harden managed\_tmp reap-root guard and disarm guard test | [sase-157.1](sase-157.1.md) | 2026-09-21 06:45:45 EDT |
