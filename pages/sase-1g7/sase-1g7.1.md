# Bead: sase-1g7.1 — Publish to one feed host from any machine

[Bead Pages](../README.md) / [sase-1g7](README.md) / sase-1g7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0wl](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0wl.md) · **Assignee:** `sase-1g7.1` · **Size:** medium
**Created:** 2026-10-04 19:02:10 EDT · **Closed:** 2026-10-04 19:34:15 EDT
**Plan:** [202610/listen\_urls\_any\_machine.md](https://github.com/sase-org/sase--plans/blob/main/202610/listen_urls_any_machine.md)

## Description

feed-host: add feed.host/feed.host_ssh config, an SSH transport that streams a rendered episode to the host's new `feed receive` endpoint (validated import, then a locked publish), proxy publish/unpublish/feed/doctor in remote mode, keep a retry outbox, and document the model.

## Notes

[2026-10-04T23:34:15Z · sase-1g7.1] Verified feed-host: config host/host_ssh + SASE_LISTEN_FEED_HOST, SSH pack/receive with extractfile (no extractall), re-entrant feed lock, remote proxy of publish/unpublish/feed/doctor, outbox + publish --pending, auto-publish queue-on-fail without changing exit, token masking, docs/multi-machine.md. sase tool run check green (aa155b1bdecfcdbcc8dd9caba1b95ab9). pytest 205 passed, 1 skipped. No leftover --epic-symbol entries.

## Dependencies

- **Blocks:** [sase-1g7.3](sase-1g7.3.md) ✓ · ⧖ 2026-10-04
- **Blocks:** [sase-1g7.4](sase-1g7.4.md) ✓ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g7.1/README.md) | [sase-1g7.1](sase-1g7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-listen | [`sase-listen@0e03944`](https://github.com/sase-org/sase-listen/commit/0e0394432210d4d7c7729328c79a4120189b0253) | feat(feed): publish episodes to one SSH feed host from any machine | [sase-1g7.1](sase-1g7.1.md) | 2026-10-04 19:39:21 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1g7.1][1] | Confirm the phase bead closed after sase bead close | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g7.1/README.md

<!-- sase:referenced-by:end -->
