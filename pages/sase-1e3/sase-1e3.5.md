# Bead: sase-1e3.5 — TTS engines, narrator profiles, credentials, retries, cache, and pricing

[Bead Pages](../README.md) / [sase-1e3](README.md) / sase-1e3.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3z](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3z.md) · **Assignee:** `sase-1e3.5` · **Size:** medium
**Created:** 2026-10-01 14:42:48 EDT
**Plan:** [202610/sase\_listen.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_listen.md)

## Description

engines: add the Engine protocol and the Gemini, OpenAI-compatible, and offline tone adapters. Add narrator profiles, secret resolution from env or command, retry with backoff, the content-addressed LRU chunk cache, and dated pricing estimates. Verify Gemini with a single live call.

## Dependencies

- **Depends on:** [sase-1e3.1](sase-1e3.1.md) ✓ · ⧖ 2026-10-01
- **Blocks:** [sase-1e3.6](sase-1e3.6.md) ◐ · ⧖ 2026-10-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1e3.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1e3.5/README.md) | [sase-1e3.5](sase-1e3.5.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.38.cdx][1] | Verify TTS engine and PyPI release evidence before stating install availability | 1 |
| read-by | [agent:research.38.cld][2] | Check phase progress/notes for sase-listen user-facing research | 1 |
| read-by | [agent:research.38.grk][3] | Need child phase scope for sase-listen user-facing research | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.cdx/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.cld/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.grk/README.md

<!-- sase:referenced-by:end -->
