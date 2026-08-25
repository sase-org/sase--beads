# Bead: sase-sq.7.1.5 — sase glossary as a deprecating alias

[Bead Pages](../README.md) / [sase-sq.7.1](sase-sq.7.1.md) / sase-sq.7.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-sq.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sq.7.md) · **Assignee:** `sase-sq.7.1.5` · **Size:** medium
**Created:** 2026-08-24 18:15:37 EDT · **Closed:** 2026-08-24 21:00:01 EDT
**Plan:** [202608/glossary\_memory\_web.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_memory_web.md)

## Description

compat: give `sase glossary read|show|all|list|log` a one-line deprecation notice naming its `sase memory` equivalent and delegate to it when the project has a glossary web, and make `sase glossary add|del` write and delete strand files instead of config entries when the web exists.

## Notes

[2026-08-25T00:59:05Z · sase-sq.7.1.5] PROPOSED FOLLOW-UP: symvision lint fails on master (pre-existing, unrelated to glossary compat work) — src/sase/bead/_project_mutations_shared.py:_combine_mutation_outcomes is imported by a non-test file while private; make it public or stop importing it cross-module.

[2026-08-25T00:59:31Z · sase-sq.7.1.5] PROPOSED FOLLOW-UP: 8 pre-existing tests/test_bead/ failures on master, unrelated to glossary compat (confirmed via git stash) — test_cli_golden.py[list_full,list_json,list_json_limit,list_implicit_closed_json,show_json,show_phase_json], test_cli_history.py::test_history_full_makes_overwritten_note_revisions_readable, test_cli_search.py::test_handle_bead_search_compact_includes_closed_and_match_reason; likely caused by the recent _project_mutations.py submixin split (notes shape/history-format drift).

[2026-08-25T01:00:01Z · sase-sq.7.1.5] Added sase/glossary/compat.py (deprecation notices + web-aware delegation for read/show/all/list/log) and sase/glossary/web_mutation.py (strand-file add/delete engine + CLI wrappers, reusing mutation.py's promoted validation helpers). Rewired src/sase/main/glossary_handler.py to check find_glossary_web() per subcommand: read/show/all/list/log always print a one-line stderr notice then delegate to the sase memory equivalent when a glossary web exists (else run the legacy handler unchanged); add/del write/delete a strand file when a web exists (else the legacy config edit). sase glossary log -p chdirs into the target project since sase memory log has no -p. Updated parser_glossary.py's group description to describe the web + compat window. Verified: just lint's ruff+mypy gates pass clean; just fmt applied; new tests (tests/main/test_glossary_compat.py, tests/test_glossary_web_mutation.py) plus all existing glossary/memory tests pass (119 glossary tests, 47 in the touched dispatcher/mutation files); just test-scoped run is clean except 8 tests/test_bead/* + a symvision violation, all confirmed pre-existing on master via git stash (unrelated bead-subsystem regression, noted as PROPOSED FOLLOW-UP). No --epic-symbol entries for this phase.

## Dependencies

- **Depends on:** [sase-sq.7.1.3](sase-sq.7.1.3.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-sq.7.1.6](sase-sq.7.1.6.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sq.7.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sq.7.1.5/README.md) | [sase-sq.7.1.5](sase-sq.7.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ec889f5`](https://github.com/sase-org/sase/commit/ec889f58788ba027631ba901c4be2232b983f5c0) | feat(glossary): add web-memory compat shim and strand mutation engine | [sase-sq.7.1.5](sase-sq.7.1.5.md) | 2026-08-24 21:01:08 EDT |
