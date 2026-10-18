# Bead: sase-1mk — Own every release blocker, green Full CI, and ship sase v0.18.0 through ci\_watch

[Bead Pages](../README.md) / sase-1mk

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.11b](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.11b.md) · **Assignee:** `sase-1mk.land`
**Created:** 2026-10-18 09:58:28 EDT
**Plan:** [202610/ship\_v0\_18\_0\_owned\_blockers.md](https://github.com/sase-org/sase--plans/blob/main/202610/ship_v0_18_0_owned_blockers.md)

## Description

sase 0.18.0 is on PyPI, published from release-please PR #299 after ci_watch merged it on a green Master Gate and a fresh green Full CI, with sase-core-rs 0.42.0 published as its core floor. The release is confirmed before landing and recorded in an evidence artifact by the final epic lander.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1mk.1](sase-1mk.1.md) | Make the core non-UTF-8 snapshot fixture filesystem-independent | ✓ closed | small | 2026-10-18 | 1 | 1 |
| [sase-1mk.2](sase-1mk.2.md) | Teach the release watcher about the core release PR | ◐ in_progress | medium | 2026-10-18 | 1 | 0 |
| [sase-1mk.3](sase-1mk.3.md) | Fix the files Ctrl-J anchor-scroll Full CI flake at its root | ◐ in_progress | medium | 2026-10-18 | 1 | 0 |
| [sase-1mk.4](sase-1mk.4.md) | Fix the archive, screenshot-export and statistics Full CI flakes | ◐ in_progress | medium | 2026-10-18 | 1 | 0 |
| [sase-1mk.5](sase-1mk.5.md) | Fix the usage-probe, git-maintenance and stderr-burst Full CI flakes | ◐ in_progress | medium | 2026-10-18 | 1 | 0 |
| [sase-1mk.6](sase-1mk.6.md) | Fix the New Project create and configure Master Gate races | ◐ in_progress | medium | 2026-10-18 | 1 | 0 |
| [sase-1mk.7](sase-1mk.7.md) | Fix the link-follow and prompt mid-word Master Gate flakes | ◐ in_progress | medium | 2026-10-18 | 1 | 0 |
| [sase-1mk.8](sase-1mk.8.md) | Watch sase-core 0.42.0 and sase 0.18.0 to PyPI and always close | ◐ in_progress | small | 2026-10-18 | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1mk: Own every release blocker, green Full CI, and ship sase v0.18.0 through ci_watch [in_progress]"]
    n1["sase-1mk.1: Make the core non-UTF-8 snapshot fixture filesystem-independent [closed]"]
    n2["sase-1mk.2: Teach the release watcher about the core release PR [in_progress]"]
    n3["sase-1mk.3: Fix the files Ctrl-J anchor-scroll Full CI flake at its root [in_progress]"]
    n4["sase-1mk.4: Fix the archive, screenshot-export and statistics Full CI flakes [in_progress]"]
    n5["sase-1mk.5: Fix the usage-probe, git-maintenance and stderr-burst Full CI flakes [in_progress]"]
    n6["sase-1mk.6: Fix the New Project create and configure Master Gate races [in_progress]"]
    n7["sase-1mk.7: Fix the link-follow and prompt mid-word Master Gate flakes [in_progress]"]
    n8["sase-1mk.8: Watch sase-core 0.42.0 and sase 0.18.0 to PyPI and always close [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n1 -.-> n8
    n2 -.-> n8
    n3 -.-> n8
    n4 -.-> n8
    n5 -.-> n8
    n6 -.-> n8
    n7 -.-> n8
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1mk.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.1/README.md) | [sase-1mk.1](sase-1mk.1.md) | 1 |
| [bbugyi200.athena.sase-1mk.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.2/README.md) | [sase-1mk.2](sase-1mk.2.md) | 0 |
| [bbugyi200.athena.sase-1mk.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.3/README.md) | [sase-1mk.3](sase-1mk.3.md) | 0 |
| [bbugyi200.athena.sase-1mk.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.4/README.md) | [sase-1mk.4](sase-1mk.4.md) | 0 |
| [bbugyi200.athena.sase-1mk.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.5/README.md) | [sase-1mk.5](sase-1mk.5.md) | 0 |
| [bbugyi200.athena.sase-1mk.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.6/README.md) | [sase-1mk.6](sase-1mk.6.md) | 0 |
| [bbugyi200.athena.sase-1mk.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.7/README.md) | [sase-1mk.7](sase-1mk.7.md) | 0 |
| [bbugyi200.athena.sase-1mk.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.8/README.md) | [sase-1mk.8](sase-1mk.8.md) | 0 |
| [bbugyi200.athena.sase-1mk.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1mk.land/README.md) | [sase-1mk](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@80dc704`](https://github.com/sase-org/sase-core/commit/80dc704a4f2e1f640f7caa9e578957669c31367d) | test(project-stats): stage non-UTF-8 snapshot fixture path in the Git index only | [sase-1mk.1](sase-1mk.1.md) | 2026-10-18 10:16:36 EDT |
