# Bead: sase-en — Make \`sase bead show\` much faster

[Bead Pages](../README.md) / sase-en

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sl.f1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sl.f1/README.md) · **Assignee:** `sase-en.land`
**Created:** 2026-08-03 12:39:41 UTC
**Plan:** [202608/bead\_show\_speed.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_show_speed.md)

## Description

`sase bead show` returns in well under a second instead of ~1.8 s (and ~3.2 s for beads that carry refs), with byte-identical output at every format, style, and wrap setting, by removing a 418-call subprocess storm, the full-CLI parser import, and two redundant full bead-store reductions.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-en.1](sase-en.1.md) | Stop re-probing git remotes and re-merging config in repo inventory | ✓ closed | medium | 1 | 1 |
| [sase-en.2](sase-en.2.md) | Build only the invoked command's subparser | ✓ closed | medium | 0 | 0 |
| [sase-en.3](sase-en.3.md) | Resolve bead detail from one bead-store read | ✓ closed | medium | 1 | 2 |
| [sase-en.4](sase-en.4.md) | End-to-end budget guard and documentation | ◐ in_progress | small | 0 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-en: Make `sase bead show` much faster [in_progress]"]
    n1["sase-en.1: Stop re-probing git remotes and re-merging config in repo inventory [closed]"]
    n2["sase-en.2: Build only the invoked command's subparser [closed]"]
    n3["sase-en.3: Resolve bead detail from one bead-store read [closed]"]
    n4["sase-en.4: End-to-end budget guard and documentation [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n4
    n2 -.-> n4
    n3 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-en.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-en.1/README.md) | [sase-en.1](sase-en.1.md) | 1 |
| [bbugyi200.athena.sase-en.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-en.3/README.md) | [sase-en.3](sase-en.3.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase | [`25e706f`](https://github.com/sase-org/sase/commit/25e706f76b593d8e3147c86fdd01cd3d457ae4b0) | perf(repo): cache inventory identity derivations | [sase-en.1](sase-en.1.md) | 2026-08-03 13:28:46 |
| sase-core | [`sase-core@5f39c3d`](https://github.com/sase-org/sase-core/commit/5f39c3dc2a1a3680f66f98c8735990b6596ac781) | perf(bead): add single-pass detail read | [sase-en.3](sase-en.3.md) | 2026-08-03 13:37:44 |
| sase | [`7a66461`](https://github.com/sase-org/sase/commit/7a66461b98890f66413bfbc67bc7a6d90b2c736f) | perf(bead): resolve detail from one core snapshot | [sase-en.3](sase-en.3.md) | 2026-08-03 13:38:10 |
