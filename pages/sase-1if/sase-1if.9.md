# Bead: sase-1if.9 — Research macros prefer sase listen

[Bead Pages](../README.md) / [sase-1if](README.md) / sase-1if.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.0n.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.0n.linker.w0.md) · **Assignee:** `sase-1if.9` · **Size:** small
**Created:** 2026-10-08 15:26:27 EDT · **Closed:** 2026-10-08 16:30:57 EDT
**Plan:** [202610/plugin\_commands.md](https://github.com/sase-org/sase--plans/blob/main/202610/plugin_commands.md)

## Description

research-macros: in the sase-research-artifacts repo, make the audio macros select sase listen first, then sase-listen, then uvx sase-listen, and update docs and pinned-string tests.

## Notes

[2026-10-08T20:30:30Z · sase-1if.9] PROPOSED FOLLOW-UP: linker `sase listen ls` recovery hint is unproven — `ls` is still a stub in sase-listen, so the three-tier `sase listen ls` / `sase-listen ls` / `uvx sase-listen ls` fallback in research_swarm.md needs end-to-end validation once `ls` ships

[2026-10-08T20:30:57Z · sase-1if.9] research-macros done in sase-research-artifacts: research_audio.md Choose-the-CLI is now sase listen -> sase-listen -> uvx sase-listen probed via render --help, later steps use <listen> placeholder with sase tool run -- <listen> render; research_swarm.md linker recovery hint updated the same three-tier way; docs/macros.md and README.md recommend sase plugin install listen with uv tool install as alternative; tests/test_macro_loading.py pins updated plus new selection-order test. Verified: just lint clean and all 74 test_macro_loading.py tests pass via sase tool run (earlier full check had 112 passed / 1 failed on a wrapped pinned string, fixed by unwrapping the sentence). Recorded PROPOSED FOLLOW-UP for the unproven ls recovery hint since ls is still a stub. No epic-symbol leftovers.

## Dependencies

- **Blocks:** [sase-1if.10](sase-1if.10.md) ◐ · ⧖ 2026-10-08
- **Depends on:** [sase-1if.2](sase-1if.2.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1if.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.9/README.md) | [sase-1if.9](sase-1if.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-research-artifacts | [`sase-research-artifacts@91e353c`](https://github.com/sase-org/sase-research-artifacts/commit/91e353c8d898b235f665382e5262f5d6cdba50df) | feat(research-artifacts): prefer sase listen CLI in audio and swarm prompts | [sase-1if.9](sase-1if.9.md) | 2026-10-08 16:32:18 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1if.9][1] | phase scope | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.9/README.md

<!-- sase:referenced-by:end -->
