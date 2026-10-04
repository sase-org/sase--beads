# Bead: sase-1g6.1 — Swarm topology, audio contract, and linker listen card

[Bead Pages](../README.md) / [sase-1g6](README.md) / sase-1g6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.0b.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.0b.linker.w0.md) · **Assignee:** `sase-1g6.1` · **Size:** medium
**Created:** 2026-10-04 18:40:08 EDT · **Closed:** 2026-10-04 19:16:32 EDT
**Plan:** [202610/research\_swarm\_listen\_card.md](https://github.com/sase-org/sase--plans/blob/main/202610/research_swarm_listen_card.md)

## Description

swarm-listen-card: in sase-research-artifacts make audio imply the linker, have audio wait on image and the linker wait on audio, give the audio agent a complete-on-failure var/artifact contract, teach the linker to write the listen card plus `audio:` frontmatter, flip the locking tests, and fix the docs drift in sase-research-artifacts and sase-listen.

## Notes

[2026-10-04T23:16:32Z · sase-1g6.1] Verified swarm topology (audio implies linker; audio waits lead[+image]; linker waits lead[+image][+audio]), audio complete-on-failure var/artifact contract, linker listen-card + audio: frontmatter, flipped locking tests (68 passed in test_macro_loading.py), and docs in sase-research-artifacts + sase-listen. sase tool run check in sase-research-artifacts succeeded (020224345c3c625e1e37e144bf475bba, exit 0). epic-symbols: no leftover --epic-symbol entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1g6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1g6.1/README.md) | [sase-1g6.1](sase-1g6.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-listen | [`sase-listen@ec1196b`](https://github.com/sase-org/sase-listen/commit/ec1196b8d2f517dd4430a90d70ad19148c4dd5c1) | docs(sase-integration): document swarm listen card and audio waits | [sase-1g6.1](sase-1g6.1.md) | 2026-10-04 19:17:55 EDT |
| sase-research-artifacts | [`sase-research-artifacts@867222d`](https://github.com/sase-org/sase-research-artifacts/commit/867222d4fb2c9825958a5a08187af0db2d7d452b) | feat(xprompts): wire audio into swarm topology and linker listen card | [sase-1g6.1](sase-1g6.1.md) | 2026-10-04 19:21:34 EDT |
