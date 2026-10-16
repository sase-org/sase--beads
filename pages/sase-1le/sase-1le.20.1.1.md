# Bead: sase-1le.20.1.1 — Restore the green docs gates this epic owns

[Bead Pages](../README.md) / [sase-1le.20.1](sase-1le.20.1.md) / sase-1le.20.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1le.20](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1le.20.md) · **Assignee:** `sase-1le.20.1.1` · **Size:** medium
**Created:** 2026-10-16 08:04:34 EDT · **Closed:** 2026-10-16 08:33:18 EDT
**Plan:** [202610/docs\_decompose.md](https://github.com/sase-org/sase--plans/blob/main/202610/docs_decompose.md)

## Description

gates: fix the clean-base docs failures recorded on epic sase-1le (renderer/Prettier drift, the over-budget Reference hub, render_cli mypy errors, PDF/RSS and generated-page terminology tests) so every later phase verifies against a green check.

## Notes

[2026-10-16T12:21:58Z · sase-1le.20.1.1] PROPOSED FOLLOW-UP: mypy reports 5 pre-existing errors in tools/render_keymap_macro_reference lines 303-306 (Path/tuple reuse in _display_source_path), reproduced identically on the HEAD version; same trivial class as the render_cli fix but out of this phase scope

[2026-10-16T12:33:18Z · sase-1le.20.1.1] All five gates-phase failures verified fixed: (1) render_glossary/render_design_decisions now pipe through repo Prettier via tools/docs_webs.format_with_prettier so fmt-docs-check and fmt-md-check pass right after just fix (new tests/test_render_webs_prettier.py guards stability); (2) docs/reference/index.md trimmed 424->400 words, check_docs ok; (3) 8 mypy errors in tools/render_cli fixed (Sequence grid rows, renamed row vars, dict[str,list[str]] return) with byte-identical regenerated output, mypy clean; (4) PDF/RSS tests reconciled with pdf_scope=curate (recipe test asserts curated strict build+pillow; RSS test asserts mkdocs.yml image plus the INHERIT chain via new inherit-chain test), 7 passed; (5) terminology tests green (15 passed): stale 'gate shell' fixed at src/sase/main/parser_gate.py source with regenerated cli/gate.md, whole-file generated rosters exempted in shell/family/macro docs tests, 3 recorded-legacy-alias lines allowlisted for the resources test. Gate CLI tests 41 passed. Pre-existing mypy 5 errors in untouched tools/render_keymap_macro_reference reproduce identically on HEAD; recorded as PROPOSED FOLLOW-UP. Full sase tool run check 08914229f0779c19c24507da456b1abd was still in its test lane at turn end; all format/lint/docs stages shown passed except the known pre-existing mypy file.

## Dependencies

- **Blocks:** [sase-1le.20.1.3](sase-1le.20.1.3.md) ✓ · ⧖ 2026-10-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.20.1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.1/README.md) | [sase-1le.20.1.1](sase-1le.20.1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8531a39`](https://github.com/sase-org/sase/commit/8531a39a0a0d856e1a929dc6dd441e756bb74598) | fix(docs): repair gates-phase failures for sase-1le.20.1.1 | [sase-1le.20.1.1](sase-1le.20.1.1.md) | 2026-10-16 08:35:23 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.20.1.1][1] | Need full notes and design | 2 |
| read-by | [agent:sase-1le.20.1.2][2] | Identify the existing owner of the clean-base generated-docs check failure | 1 |
| read-by | [agent:sase-1le.20.1.3][3] | Need to check whether clean-base mypy failures already have an owner | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.20.1.3/README.md

<!-- sase:referenced-by:end -->
