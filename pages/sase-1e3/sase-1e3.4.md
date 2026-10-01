# Bead: sase-1e3.4 — Mastering, MP3 packaging, chapters, and cover art

[Bead Pages](../README.md) / [sase-1e3](README.md) / sase-1e3.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3z](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3z.md) · **Assignee:** `sase-1e3.4` · **Size:** medium
**Created:** 2026-10-01 14:42:46 EDT
**Plan:** [202610/sase\_listen.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_listen.md)

## Description

audio: resolve ffmpeg (bundled imageio-ffmpeg fallback). Trim silence and assemble PCM with gaps, then run two-pass loudnorm to a 64 kb/s mono MP3. Write ID3v2.3 tags, CHAP/CTOC chapters, and cover art, including the generated title-card design.

## Dependencies

- **Depends on:** [sase-1e3.1](sase-1e3.1.md) ✓ · ⧖ 2026-10-01
- **Blocks:** [sase-1e3.6](sase-1e3.6.md) ◐ · ⧖ 2026-10-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1e3.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1e3.4/README.md) | [sase-1e3.4](sase-1e3.4.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.38.cld][1] | Check phase progress/notes for sase-listen user-facing research | 1 |
| read-by | [agent:research.38.grk][2] | Need child phase scope for sase-listen user-facing research | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.grk/README.md

<!-- sase:referenced-by:end -->
