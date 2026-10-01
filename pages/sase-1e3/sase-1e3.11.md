# Bead: sase-1e3.11 — First releases to PyPI

[Bead Pages](../README.md) / [sase-1e3](README.md) / sase-1e3.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3z](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3z.md) · **Assignee:** `sase-1e3.11` · **Size:** small
**Created:** 2026-10-01 14:43:00 EDT · **Closed:** 2026-10-01 18:40:06 EDT
**Plan:** [202610/sase\_listen.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_listen.md)

## Description

release: verify master CI and the built wheel. Propose merging the sase-listen 0.1.0 release-please PR, plus the sase-telegram and sase-research-artifacts release PRs, through gates, then confirm that trusted publishing put each version on PyPI.

## Notes

[2026-10-01T22:12:21Z · sase-1e3.11] Verified: sase-listen master CI green (run 36932551874) and Docs deploy green (run 36932551872) on d3cb303; local wheel build contains data/guide.md, data/lexicon.yml, data/pricing.yml, data/sample.txt, data/fonts/Inter.ttf + OFL.txt (59 files). sase-telegram audio already released: v0.4.24 tag + PyPI 0.4.24 include 8cb6728 sendAudio work — no action needed.

[2026-10-01T22:12:37Z · sase-1e3.11] Release-please cannot open PRs in sase-listen: publish runs fail with "GitHub Actions is not permitted to create or approve pull requests". Bot branch release-please--branches--master--components--sase-listen (668d019, chore(master): release 0.1.0) existed on origin; created PR sase-org/sase-listen#1 from it manually. Merge method: squash (mirrors telegram #35).

[2026-10-01T22:12:53Z · sase-1e3.11] PROPOSED FOLLOW-UP: add SASE_RELEASE_TOKEN secret and fix workflow can_approve_pull_request_reviews permission in sase-listen so future release-please runs can open PRs and trigger CI without manual PR creation

[2026-10-01T22:16:54Z · sase-1e3.11] Fixed release branch with uv.lock refresh (3e35a63); sase-listen#1 CI green on all legs (title, macos 3.12, ubuntu 3.12-full/3.13/3.14). Artifacts#2 green+mergeable, head includes latest master fix. Creating one merge gate (listen#1 + artifacts#2, squash); successor verifies publish runs + PyPI and closes.

[2026-10-01T22:18:50Z · sase-1e3.11] Gate-turn creation is broken in this env (missing_gate_turn_row), so filed durable non-turn gate custom-fbaf45ea-6d5d-414e-8841-143538e37a39 in panel releases: (merge_listen sase-listen#1 AND merge_artifacts artifacts#2, squash) OR defer. Handing to gate-wait monitor; follow-up verifies publish runs + PyPI and closes.

[2026-10-01T22:20:22Z · sase-1e3.11] PROPOSED FOLLOW-UP: gate-turn creation fails (missing_gate_turn_row) and monitor start fails for bead-assigned agent lane (NameCollisionError); release merge gate filed as non-turn gate + no monitor follow-up possible, successor must verify publish/PyPI manually

## Dependencies

- **Depends on:** [sase-1e3.10](sase-1e3.10.md) ✓ · ⧖ 2026-10-01
- **Blocks:** [sase-1e3.12](sase-1e3.12.md) ✓ · ⧖ 2026-10-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1e3.11](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1e3.11/README.md) | [sase-1e3.11](sase-1e3.11.md) | 0 |

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
