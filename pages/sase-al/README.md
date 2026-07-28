# Bead: sase-al — Fix GitHub Actions failures (sase-core clippy + published-core minimum)

[Bead Pages](../README.md) / sase-al

**Status:** ◎ claimed · **Type:** plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-al.land--code`
**Created:** 2026-07-28 21:36:55 UTC · **Closed:** 2026-07-28 23:03:57 UTC
**Plan:** [202607/fix\_ci\_core\_clippy\_and\_minimum.md](https://github.com/sase-org/sase--plans/blob/main/202607/fix_ci_core_clippy_and_minimum.md)

## Description

sase-core master CI and sase master CI are both fully green: the clippy lints from the close-note change are fixed, sase-core-rs 0.12.5 (plan-header wire schema 2) is published to PyPI, and the sase repo requires it as its published-core minimum.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-al.1](sase-al.1.md) | Fix sase-core clippy lints and release 0.12.5 | ✓ closed | small | 1 | 0 |
| [sase-al.2](sase-al.2.md) | Bump the sase published-core minimum to 0.12.5 | ✓ closed | small | 1 | 1 |

## Lineage

```mermaid
flowchart TD
    n0["sase-al: Fix GitHub Actions failures (sase-core clippy + published-core minimum) [claimed]"]
    n1["sase-al.1: Fix sase-core clippy lints and release 0.12.5 [closed]"]
    n2["sase-al.2: Bump the sase published-core minimum to 0.12.5 [closed]"]
    n0 --> n1
    n0 --> n2
    n1 -.-> n2
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-al.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-al.1/README.md) | [sase-al.1](sase-al.1.md) | 0 |
| [bbugyi200.athena.sase-al.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-al.2/README.md) | [sase-al.2](sase-al.2.md) | 1 |
| [bbugyi200.athena.sase-al.land--code](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-al.land.md#member-code) | [sase-al](README.md) | 1 |
| [bbugyi200.athena.sase-al.land--plan](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-al.land.md#member-plan) | [sase-al](README.md) | 0 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`ab6f07a`](https://github.com/sase-org/sase/commit/ab6f07a68c63a7a8438942980ca20e133748dc90) | build(deps): bump published core minimum to 0.12.5 | [sase-al.2](sase-al.2.md) | 2026-07-28 22:45:24 |
| [`41a01b3`](https://github.com/sase-org/sase/commit/41a01b397c79303acad241f2a44822193b3aeb32) | ci: emit valid split SDD store record | [sase-al](README.md) | 2026-07-28 23:12:14 |
