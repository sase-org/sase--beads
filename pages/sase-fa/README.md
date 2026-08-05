# Bead: sase-fa — Revert async sidecar publication so \`sase commit\` publishes sidecars inline again

[Bead Pages](../README.md) / sase-fa

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.t4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.t4/README.md) · **Assignee:** `sase-fa.land`
**Created:** 2026-08-05 14:26:21 EDT
**Plan:** [202608/revert\_async\_sidecar\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_async_sidecar_publication.md)

## Description

`sase commit` once again publishes to every appropriate sidecar repo (agents, beads, plans) before it returns, so the `SASE_AGENT` footer URL resolves as soon as the commit lands. The `sidecar_publication` chop and the `publications` lumberjack are removed, the durable outbox is narrowed back to agent-hood retries, the agents sidecar corruption that is currently blocking all publication is repaired, and this project's agents repo is fully synced.

## Phases

| Bead | Title | Status | Size | Agents | Commits |
|---|---|---|---|---:|---:|
| [sase-fa.1](sase-fa.1.md) | Restore synchronous sidecar publication on the commit path | ✓ closed | medium | 1 | 1 |
| [sase-fa.2](sase-fa.2.md) | Remove the sidecar\_publication chop and publications lumberjack | ✓ closed | medium | 1 | 1 |
| [sase-fa.3](sase-fa.3.md) | Narrow the durable outbox back to agent-hood retries | ✓ closed | medium | 1 | 1 |
| [sase-fa.4](sase-fa.4.md) | Repair the agents sidecar digest corruption blocking all publication | ✓ closed | medium | 1 | 1 |
| [sase-fa.5](sase-fa.5.md) | Docs, end-to-end verification, agents-repo sync, and bead bookkeeping | ◐ in_progress | small | 1 | 0 |

## Lineage

```mermaid
flowchart TD
    n0["sase-fa: Revert async sidecar publication so `sase commit` publishes sidecars inline again [in_progress]"]
    n1["sase-fa.1: Restore synchronous sidecar publication on the commit path [closed]"]
    n2["sase-fa.2: Remove the sidecar_publication chop and publications lumberjack [closed]"]
    n3["sase-fa.3: Narrow the durable outbox back to agent-hood retries [closed]"]
    n4["sase-fa.4: Repair the agents sidecar digest corruption blocking all publication [closed]"]
    n5["sase-fa.5: Docs, end-to-end verification, agents-repo sync, and bead bookkeeping [in_progress]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n1 -.-> n2
    n1 -.-> n5
    n2 -.-> n3
    n2 -.-> n5
    n3 -.-> n5
    n4 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fa.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fa.1/README.md) | [sase-fa.1](sase-fa.1.md) | 1 |
| [bbugyi200.athena.sase-fa.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fa.2/README.md) | [sase-fa.2](sase-fa.2.md) | 1 |
| [bbugyi200.athena.sase-fa.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fa.3/README.md) | [sase-fa.3](sase-fa.3.md) | 1 |
| [bbugyi200.athena.sase-fa.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fa.4/README.md) | [sase-fa.4](sase-fa.4.md) | 1 |
| [bbugyi200.athena.sase-fa.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fa.5/README.md) | [sase-fa.5](sase-fa.5.md) | 0 |
| [bbugyi200.athena.sase-fa.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fa.land/README.md) | [sase-fa](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2a9627b`](https://github.com/sase-org/sase/commit/2a9627bc0814c495b8b5a99145eb7c17c72059ee) | fix(agents-sync): repair stale hood-snapshot digests and add drift check | [sase-fa.4](sase-fa.4.md) | 2026-08-05 15:20:33 EDT |
| sase | [`de78052`](https://github.com/sase-org/sase/commit/de7805278926e3a9abd97b475afca158363d7ffc) | fix: publish sidecar work inline on the commit path | [sase-fa.1](sase-fa.1.md) | 2026-08-05 15:51:02 EDT |
| sase | [`e99f501`](https://github.com/sase-org/sase/commit/e99f5017d39fc15f6a8f5082fbd82ed2d768a2db) | feat!: remove the sidecar\_publication chop and publications lumberjack | [sase-fa.2](sase-fa.2.md) | 2026-08-05 16:17:49 EDT |
| sase | [`ccf4d77`](https://github.com/sase-org/sase/commit/ccf4d77a9b1ffe83936e81c082040d61d2b8af60) | feat!: narrow the durable publication outbox back to agent-hood retries | [sase-fa.3](sase-fa.3.md) | 2026-08-05 17:10:00 EDT |
