# Bead: sase-1g7 — sase-listen: URL-to-podcast editions, published from any machine

[Bead Pages](../README.md) / sase-1g7

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0wl](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0wl.md) · **Assignee:** `sase-1g7.land`
**Created:** 2026-10-04 19:02:08 EDT
**Plan:** [202610/listen\_urls\_any\_machine.md](https://github.com/sase-org/sase--plans/blob/main/202610/listen_urls_any_machine.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/listen_urls_any_machine.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/listen_urls_any_machine.md

<!-- sase:links:end -->

## Description

From athena, apollo, or the Mac, `sase-listen render <URL> --edition brief|full` fetches a web article, writes a fidelity-checked narration script, renders it, and auto-publishes the episode to the single AntennaPod feed served from apollo. This is proven by a full edition of OpenAI's harness-engineering post, rendered on athena, appearing in the live served feed.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-1g7.1](sase-1g7.1.md) | Publish to one feed host from any machine | ✓ closed | medium | 2026-10-04 | 1 | 1 |
| [sase-1g7.2](sase-1g7.2.md) | Fetch and extract web articles as render sources | ✓ closed | medium | 2026-10-04 | 1 | 1 |
| [sase-1g7.3](sase-1g7.3.md) | Brief and full article editions with a script writer | ✓ closed | medium | 2026-10-04 | 1 | 1 |
| [sase-1g7.4](sase-1g7.4.md) | Roll out to every machine and publish the harness-engineering full edition | ✓ closed | medium | 2026-10-04 | 1 | 2 |

## Lineage

```mermaid
flowchart TD
    n0["sase-1g7: sase-listen: URL-to-podcast editions, published from any machine [in_progress]"]
    n1["sase-1g7.1: Publish to one feed host from any machine [closed]"]
    n2["sase-1g7.2: Fetch and extract web articles as render sources [closed]"]
    n3["sase-1g7.3: Brief and full article editions with a script writer [closed]"]
    n4["sase-1g7.4: Roll out to every machine and publish the harness-engineering full edition [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n1 -.-> n3
    n1 -.-> n4
    n2 -.-> n3
    n2 -.-> n4
    n3 -.-> n4
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g7.1/README.md) | [sase-1g7.1](sase-1g7.1.md) | 1 |
| [bbugyi200.athena.sase-1g7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g7.2/README.md) | [sase-1g7.2](sase-1g7.2.md) | 1 |
| [bbugyi200.athena.sase-1g7.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g7.3/README.md) | [sase-1g7.3](sase-1g7.3.md) | 1 |
| [bbugyi200.athena.sase-1g7.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g7.4.md) | [sase-1g7.4](sase-1g7.4.md) | 2 |
| [bbugyi200.athena.sase-1g7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g7.land/README.md) | [sase-1g7](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-listen | [`sase-listen@e085c63`](https://github.com/sase-org/sase-listen/commit/e085c63bc509d4d2dab076842c461961dce37f52) | feat(web): fetch and render article URLs | [sase-1g7.2](sase-1g7.2.md) | 2026-10-04 19:30:39 EDT |
| sase-listen | [`sase-listen@0e03944`](https://github.com/sase-org/sase-listen/commit/0e0394432210d4d7c7729328c79a4120189b0253) | feat(feed): publish episodes to one SSH feed host from any machine | [sase-1g7.1](sase-1g7.1.md) | 2026-10-04 19:39:21 EDT |
| sase-listen | [`sase-listen@9f491ac`](https://github.com/sase-org/sase-listen/commit/9f491ac5d51cf7fedc8700c3d3adef6f0d45e232) | feat(writer): add brief and full article editions | [sase-1g7.3](sase-1g7.3.md) | 2026-10-04 20:19:04 EDT |
| chezmoi | [`chezmoi@9e8d272`](https://github.com/bbugyi200/dotfiles/commit/9e8d272ca6d195b1290869ec1155a51dcc592ae3) | feat(sase-listen): point feed.host at apollo for multi-machine publish | [sase-1g7.4](sase-1g7.4.md) | 2026-10-04 21:13:45 EDT |
| sase-listen | [`sase-listen@69a52a4`](https://github.com/sase-org/sase-listen/commit/69a52a449a421126197748025fd0e3111fc38233) | fix(feed): report remote via as the SSH destination | [sase-1g7.4](sase-1g7.4.md) | 2026-10-04 21:17:35 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1g7.4--1][1] | Confirm parent epic still open after phase close | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g7.4.md

<!-- sase:referenced-by:end -->
