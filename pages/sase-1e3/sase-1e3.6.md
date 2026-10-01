# Bead: sase-1e3.6 — Render orchestration, quality gates, manifest, and episode library

[Bead Pages](../README.md) / [sase-1e3](README.md) / sase-1e3.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3z](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3z.md) · **Assignee:** `sase-1e3.6` · **Size:** medium
**Created:** 2026-10-01 14:42:50 EDT · **Closed:** 2026-10-01 16:04:56 EDT
**Plan:** [202610/sase\_listen.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_listen.md)

## Description

pipeline: wire `render`, which takes a script, Markdown, or artifact ref and produces an MP3 with chunk planning, concurrency, intro and outro, chunk- and episode-level quality gates with targeted re-synthesis, the manifest, an atomic library commit, locks, `--json`, and exit codes. Prove it end to end with the tone engine.

## Notes

[2026-10-01T20:04:23Z · sase-1e3.6] PROPOSED FOLLOW-UP: repo-wide coverage is 86% vs the new fail_under=90 (pipeline files are 97-100%); the cli phase (sase-1e3.7) snapshot tests for doctor/config/ls/audition/cache/feed commands plus feed.py will close the gap

[2026-10-01T20:04:56Z · sase-1e3.6] render pipeline done: source loading (script/Markdown/ref), greedy chunk planning with intro/outro, pooled synthesis with immediate caching, hard/soft gates with re-synthesis, mastering+ID3+cover, episode gates, atomic library commit with fcntl lock, --json and exit codes 0-6. Verified: sase tool run check green (ruff+format+mypy-strict+codespell, 169 passed 1 skipped), tone e2e incl. golden fixture, resume, gate resynthesis, lint refuse/force, fake-sase ref, json schemas, publish smoke simulated OK, docs reliability+architecture updated, coverage fail_under raised to 90

## Dependencies

- **Depends on:** [sase-1e3.3](sase-1e3.3.md) ✓ · ⧖ 2026-10-01
- **Depends on:** [sase-1e3.4](sase-1e3.4.md) ✓ · ⧖ 2026-10-01
- **Depends on:** [sase-1e3.5](sase-1e3.5.md) ✓ · ⧖ 2026-10-01
- **Blocks:** [sase-1e3.7](sase-1e3.7.md) ◐ · ⧖ 2026-10-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1e3.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1e3.6/README.md) | [sase-1e3.6](sase-1e3.6.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.38.cld][1] | Check phase progress/notes for sase-listen user-facing research | 1 |
| read-by | [agent:research.38.grk][2] | Need child phase scope for sase-listen user-facing research | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.grk/README.md

<!-- sase:referenced-by:end -->
