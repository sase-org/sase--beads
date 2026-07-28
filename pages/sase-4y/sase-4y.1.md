# Bead: sase-4y.1 — Phase 1 - Data layer: unified sources, model, dates

[Bead Pages](../README.md) / [sase-4y](README.md) / sase-4y.1

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-4y.1`
**Created:** 2026-06-19 01:44:28 UTC · **Closed:** 2026-06-19 02:23:58 UTC
**Plan:** [202606/prompt\_search\_command.md](https://github.com/sase-org/sase--plans/blob/main/202606/prompt_search_command.md)

## Description

Build the unified prompt corpus: PromptHit model, SDD/local loaders, de-duplication, date parsing, and focused tests.

## Notes

COMMIT: 394c11134

[2026-07-27T21:35:48Z · sase-a1.land] [2026-06-19T02:16:05Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Phase 1 data layer landed (pure Python, no CLI/render). New package src/sase/prompt/search/: model.py (PromptSource StrEnum, PromptHit, PromptSearchMatch, PromptSearchResult), dates.py (parse_search_date incl. YYYYMM/YYmmdd/YYmmdd_HHMMSS/relative Nd|Nw|Nm|Ny; resolve_sdd_date precedence frontmatter->path YYYYMM->mtime; hit_date), sources.py (load_sdd_prompt_hits across canonical/legacy-root/local layouts, load_local_prompt_hits adapter over list_prompt_records, collect_prompt_hits unifier + sha-based dedup preferring SDD with also_in_local). Tests: tests/prompt_command/test_search_dates.py + test_search_sources.py (50 tests, all green). Decision: tags = SDD prompt_tags frontmatter + #xprompt chip names only; runner-control %directives (model/name/group/...) intentionally excluded as noise. just check is green for fmt/lint(ruff,mypy,keep-sorted,pyvision,pyscripts); the only failing tests (6x bead_search in test_bead/test_cli_search.py + test_core_facade) are a PRE-EXISTING stale sase_core_rs Rust wheel lacking the bead_search binding -- unrelated to this Python-only change.

## Dependencies

- **Blocks:** [sase-4y.2](sase-4y.2.md) ✓
- **Blocks:** [sase-4y.3](sase-4y.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-4y.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-4y.1/README.md) | [sase-4y.1](sase-4y.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`30faa26`](https://github.com/sase-org/sase/commit/30faa263b09db638d8feb6de1d15333df3ab5786) | feat(prompt): add unified prompt search data layer (Phase 1) (sase-4y.1) | [sase-4y.1](sase-4y.1.md) | 2026-06-19 02:25:47 |
