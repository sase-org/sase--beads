# Bead: sase-1g7.2 — Fetch and extract web articles as render sources

[Bead Pages](../README.md) / [sase-1g7](README.md) / sase-1g7.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0wl](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0wl.md) · **Assignee:** `sase-1g7.2` · **Size:** medium
**Created:** 2026-10-04 19:02:12 EDT · **Closed:** 2026-10-04 19:29:15 EDT
**Plan:** [202610/listen\_urls\_any\_machine.md](https://github.com/sase-org/sase--plans/blob/main/202610/listen_urls_any_machine.md)

## Description

url-acquire: fetch pages with curl_cffi browser impersonation, extract with Trafilatura plus HTML outline repair, keep a per-source store, add the `article` kind, and accept http(s) URLs in `script`/`render` for the deterministic verbatim edition.

## Notes

[2026-10-04T23:29:15Z · sase-1g7.2] Implemented local URL article fetch/extract/store, article scripts, URL render integration, CLI options, and docs. Verified with sase tool run check (green), uv run mkdocs build --strict, and no remaining epic symbols.

## Dependencies

- **Blocks:** [sase-1g7.3](sase-1g7.3.md) ✓ · ⧖ 2026-10-04
- **Blocks:** [sase-1g7.4](sase-1g7.4.md) ✓ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g7.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g7.2/README.md) | [sase-1g7.2](sase-1g7.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-listen | [`sase-listen@e085c63`](https://github.com/sase-org/sase-listen/commit/e085c63bc509d4d2dab076842c461961dce37f52) | feat(web): fetch and render article URLs | [sase-1g7.2](sase-1g7.2.md) | 2026-10-04 19:30:39 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1g7.2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g7.2/README.md

<!-- sase:referenced-by:end -->
