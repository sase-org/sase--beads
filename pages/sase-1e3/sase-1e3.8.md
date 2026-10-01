# Bead: sase-1e3.8 — Private podcast feed for AntennaPod

[Bead Pages](../README.md) / [sase-1e3](README.md) / sase-1e3.8

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3z](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3z.md) · **Assignee:** `sase-1e3.8` · **Size:** medium
**Created:** 2026-10-01 14:42:54 EDT
**Plan:** [202610/sase\_listen.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_listen.md)

## Description

feed: add `feed init`/`feed`/`publish`/`unpublish`. Publishing writes into a served-only feed directory with an RSS 2.0 + iTunes + Podcasting 2.0 feed.xml, per-episode chapters JSON, and generated channel art. Add retention, auto-publish for research episodes, a token-path URL with a QR code, and Tailscale Funnel serving docs.

## Dependencies

- **Blocks:** [sase-1e3.10](sase-1e3.10.md) ◐ · ⧖ 2026-10-01
- **Depends on:** [sase-1e3.7](sase-1e3.7.md) ◐ · ⧖ 2026-10-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1e3.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1e3.8/README.md) | [sase-1e3.8](sase-1e3.8.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.38.cld][1] | Check phase progress/notes for sase-listen user-facing research | 1 |
| read-by | [agent:research.38.grk][2] | Need child phase scope for sase-listen user-facing research | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.grk/README.md

<!-- sase:referenced-by:end -->
