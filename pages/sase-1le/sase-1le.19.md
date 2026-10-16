# Bead: sase-1le.19 — One-screen homepage, front-door link retargeting, and reader-testing kit

[Bead Pages](../README.md) / [sase-1le](README.md) / sase-1le.19

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4l.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4l.linker.w0.md) · **Assignee:** `sase-1le.19` · **Size:** medium
**Created:** 2026-10-15 18:11:14 EDT · **Closed:** 2026-10-15 23:18:34 EDT
**Plan:** [202610/sase\_sh\_docs\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_sh_docs_redesign.md)

## Description

homepage: rebuild index.md around one primary CTA, install, one demo, four capability cards, and four doors; retarget README and TUI onboarding links; add the observed-reader kit.

## Notes

[2026-10-16T03:18:09Z · sase-1le.19] PROPOSED FOLLOW-UP: renderer/prettier war breaks fmt-docs-check and glossary tooltips — tools/render_glossary emits *emphasis* one-per-line but prettier rewrites abbreviations.md/glossary.md/design-decisions.md to _emphasis_ wrapped, so just fmt-docs-check fails on the clean base tree (see epic bead note from sase-1le.9) and the mangled *[term]: defs render as a visible glossary dump with zero <abbr> tooltips site-wide; owned by sase-1le.8 pipeline, needs land-agent triage

[2026-10-16T03:18:18Z · sase-1le.19] PROPOSED FOLLOW-UP: strict docs-check fails on stale getting_started links — docs/concepts/automation.md, memory.md, prompts.md still link ../getting_started.md, deleted when sase-1le.9 moved it to start/; fails identically on clean HEAD, blocks the strict build before check_docs_urls runs (URL contract itself passes: 285 URLs green)

[2026-10-16T03:18:34Z · sase-1le.19] Homepage rebuilt: one primary CTA (start/first-run) + secondary (concepts), 3-line install block with copy, status pill (Alpha/Linux+macOS/authenticated CLI verified against README+install.md), fanout mp4 demo with poster/controls/no-autoplay, 4 capability cards to concept pages, 4 doors, footer row (essay/blog/handbook/acks); role cards/primitives/next-click grid removed and sase-* CSS trimmed (extra.css+pdf.css). README Learn more rewritten around 4 doors + 4 guides; TUI onboarding (agent/axe/patch) + parser_sudo retargeted to concepts/* with tests updated (20 passed). reader-testing.md + nav/hub entries added. Verified: check_docs ok, URL contract 285/285 green, mypy clean, Playwright 1280x800 (install+demo above fold) + 390px drawer checked. Pre-existing clean-tree failures recorded as PROPOSED FOLLOW-UPs (fmt-docs-check renderer/prettier drift; strict build getting_started links); budgets ratcheted index.md 922->361

## Dependencies

- **Depends on:** [sase-1le.12](sase-1le.12.md) ✓ · ⧖ 2026-10-15
- **Depends on:** [sase-1le.13](sase-1le.13.md) ✓ · ⧖ 2026-10-15
- **Blocks:** [sase-1le.20](sase-1le.20.md) ◐ · ⧖ 2026-10-15
- **Depends on:** [sase-1le.3](sase-1le.3.md) ✓ · ⧖ 2026-10-15
- **Depends on:** [sase-1le.9](sase-1le.9.md) ✓ · ⧖ 2026-10-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.19](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.19/README.md) | [sase-1le.19](sase-1le.19.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8676f92`](https://github.com/sase-org/sase/commit/8676f92f2f0d2c4cc1ce3580f4bc835af09144ad) | feat(docs): rebuild homepage as one-screen front door with reader-testing kit (sase-1le.19) | [sase-1le.19](sase-1le.19.md) | 2026-10-15 23:20:09 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.19][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.19/README.md

<!-- sase:referenced-by:end -->
