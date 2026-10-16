# Bead: sase-1le.3 — Declare which version the docs describe and smoke the documented install

[Bead Pages](../README.md) / [sase-1le](README.md) / sase-1le.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4l.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4l.linker.w0.md) · **Assignee:** `sase-1le.3` · **Size:** small
**Created:** 2026-10-15 18:11:09 EDT · **Closed:** 2026-10-15 19:00:19 EDT
**Plan:** [202610/sase\_sh\_docs\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_sh_docs_redesign.md)

## Description

applicability: add a generated latest-release line to the site header, single-source the documented install command, and schedule a clean PyPI install smoke.

## Notes

[2026-10-15T23:00:06Z · sase-1le.3] PROPOSED FOLLOW-UP: Dated blog posts still show bare install commands - hello-sase-your-first-15-minutes.md, why-coding-agents-need-orchestration.md (4 fences), structured-agentic-software-engineering.md (3 fences); start/homepage phases should decide whether dated essays get the sase>=0.18 floor

[2026-10-15T23:00:11Z · sase-1le.3] PROPOSED FOLLOW-UP: sase doctor -j in this checkout exits 1 on a #research/audio macro edition-arg ERROR unrelated to this phase diff; confirm the install-smoke doctor step is meaningful on a clean PyPI install once 0.18 ships

[2026-10-15T23:00:19Z · sase-1le.3] Verified: tools/render_applicability --check green (floor uv tool install sase>=0.18 single-sourced; 5 docs carry it); 7 new applicability tests + all 15 justfile-lint tests green; just fmt and strict mkdocs build green with dismissible v0.18-pending banner rendered in site/index.html and hidden from the PDF config; full sase tool run check: every lint stage and 55905 scoped tests passed except test_fix_uses_formatter_venv_without_application_setup (its just-fix sandbox lacked a stub for the new fmt-docs line) - root-caused, sandbox extended, green on re-run. PyPI resolution today: max sase 0.17.1, so the documented floor command fails loudly (only sase<=0.17.1 available) instead of silently installing 0.1.0; the daily install-smoke workflow will report that real resolver failure until 0.18 ships. No epic-symbol entries. Handoff for start phase (sase-1le.9): re-point DOCUMENTED_COMMAND_FILES / promote the constant into render_docs when getting_started.md moves.

## Dependencies

- **Blocks:** [sase-1le.19](sase-1le.19.md) ✓ · ⧖ 2026-10-15
- **Blocks:** [sase-1le.9](sase-1le.9.md) ✓ · ⧖ 2026-10-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.3/README.md) | [sase-1le.3](sase-1le.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`741afba`](https://github.com/sase-org/sase/commit/741afba3b5ab8da15d0ce9060268a902b657d39a) | feat(docs): declare documented version and smoke the install (sase-1le.3) | [sase-1le.3](sase-1le.3.md) | 2026-10-15 19:01:30 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1le.3][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.3/README.md

<!-- sase:referenced-by:end -->
