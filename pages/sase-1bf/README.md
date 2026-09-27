# Bead: sase-1bf — Bound agent scratch by ownership, not by environment luck

[Bead Pages](../README.md) / sase-1bf

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.1d` · **Assignee:** `sase-1bf.land`
**Created:** 2026-09-27 14:23:29 EDT
**Plan:** [202609/bounded\_agent\_scratch.md](https://github.com/sase-org/sase--plans/blob/main/202609/bounded_agent_scratch.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/bounded_agent_scratch.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/bounded_agent_scratch.md

<!-- sase:links:end -->

## Description

Per-launch agent scratch (cargo targets, agent TMPDIRs) is removed when its launch is dead, on every managed temp root any writer actually used, regardless of which environment the service host was started with; cleanup refusals are visible; and `sase disk list` / disk-pressure notifications account for where the bytes really are, so a SASE host can no longer silently fill its disk.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1bf.1](sase-1bf.1.md) | Managed temp root registry the reaper follows | ◐ in_progress | medium | 2026-09-27 | 1 | 1 |
| [sase-1bf.2](sase-1bf.2.md) | Rust-owned launch scratch liveness that works under systemd | ✓ closed | medium | 2026-09-27 | 1 | 1 |
| [sase-1bf.3](sase-1bf.3.md) | Dead-launch backstop pass and liveness-aware pressure | ◐ in_progress | medium | 2026-09-27 | 1 | 0 |
| [sase-1bf.4](sase-1bf.4.md) | Truthful disk attribution under pressure | ◐ in_progress | medium | 2026-09-27 | 1 | 0 |
| [sase-1bf.5](sase-1bf.5.md) | Retention for visual snapshot run reports | ✓ closed | small | 2026-09-27 | 1 | 1 |
| [sase-1bf.6](sase-1bf.6.md) | Integrated acceptance on apollo and athena | ◐ in_progress | small | 2026-09-27 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1bf: Bound agent scratch by ownership, not by environment luck [in_progress]"]
    n1["sase-1bf.1: Managed temp root registry the reaper follows [in_progress]"]
    n2["sase-1bf.2: Rust-owned launch scratch liveness that works under systemd [closed]"]
    n3["sase-1bf.3: Dead-launch backstop pass and liveness-aware pressure [in_progress]"]
    n4["sase-1bf.4: Truthful disk attribution under pressure [in_progress]"]
    n5["sase-1bf.5: Retention for visual snapshot run reports [closed]"]
    n6["sase-1bf.6: Integrated acceptance on apollo and athena [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n1 -.-> n3
    n1 -.-> n4
    n1 -.-> n6
    n2 -.-> n3
    n2 -.-> n6
    n3 -.-> n6
    n4 -.-> n6
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bf.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bf.1.md) | [sase-1bf.1](sase-1bf.1.md) | 1 |
| [bbugyi200.apollo.sase-1bf.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1bf.2.md) | [sase-1bf.2](sase-1bf.2.md) | 1 |
| [bbugyi200.apollo.sase-1bf.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bf.3/README.md) | [sase-1bf.3](sase-1bf.3.md) | 0 |
| [bbugyi200.apollo.sase-1bf.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bf.4/README.md) | [sase-1bf.4](sase-1bf.4.md) | 0 |
| [bbugyi200.apollo.sase-1bf.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bf.5/README.md) | [sase-1bf.5](sase-1bf.5.md) | 1 |
| [bbugyi200.apollo.sase-1bf.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bf.6/README.md) | [sase-1bf.6](sase-1bf.6.md) | 0 |
| [bbugyi200.apollo.sase-1bf.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bf.land/README.md) | [sase-1bf](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d99f478`](https://github.com/sase-org/sase/commit/d99f4789e9c9bf2b49c6b76a77deb212da162389) | feat(visual): prune old screenshot maintenance run reports | [sase-1bf.5](sase-1bf.5.md) | 2026-09-27 14:37:05 EDT |
| sase | [`7e4482a`](https://github.com/sase-org/sase/commit/7e4482a62fe63645c36f73439d6abc79150837d4) | feat(scratch): rust-owned launch scratch liveness with systemd-safe probe | [sase-1bf.2](sase-1bf.2.md) | 2026-09-27 15:32:24 EDT |
| sase | [`40295ea`](https://github.com/sase-org/sase/commit/40295eaf543f8e64e1e34c0862bce1411a353a42) | feat(managed-tmp): add Rust-owned root registry the reaper follows (sase-1bf.1) | [sase-1bf.1](sase-1bf.1.md) | 2026-09-27 17:19:10 EDT |
