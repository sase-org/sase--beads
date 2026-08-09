# Bead: sase-i1.4 — Finish and land opt-in regex bead search

[Bead Pages](../README.md) / [sase-i1](README.md) / sase-i1.4

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-i1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i1.land/README.md) · **Assignee:** `sase-i1.4.land`
**Created:** 2026-08-09 09:05:11 EDT
**Plan:** [202608/bead\_search\_regex\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_search_regex_landing.md)

## Description

Epic sase-i1 is complete in normal published installs and local development: regex matching works consistently in both lanes, literal search keeps its cheap substring path, the released core floor is correct, all follow-ups are routed, and the epic is closed with its linked plan marked done.

## Notes

[2026-08-09T13:13:07Z · we] DISCOVERED ISSUE: Independent reproduction while verifying an unrelated glossary-title change at a3a536a03. After just install, the focused glossary tests pass, but just check escalates to the full suite and fails in bead search because src/sase/core/bead_read_facade.py passes regex= to the Rust bead_search binding while the installed/built binding rejects it: TypeError: bead_search() got an unexpected keyword argument 'regex'. Focused rerun reproduces with .venv/bin/pytest tests/test_bead/test_cli_search.py tests/test_bead/test_cli_show_json.py::test_search_json_keeps_phase_size_in_machine_output tests/test_core_facade/test_bead_read.py::test_read_facade_matches_bead_project_queries -q -> 15 failed, 5 passed. This matches the active published-binding-floor work already described on sase-i1/sase-i1.4, so no standalone task bead was created.

[2026-08-09T13:23:52Z · wf] DISCOVERED ISSUE: Independent reproduction during unrelated prompt-glossary verification on 2026-08-09 at ~09:19 EDT. After 'just install', focused glossary tests and 'just test-visual' passed, but 'just check' escalated to the full suite and failed in bead search tests because src/sase/core/bead_read_facade.py passes regex= to bead_search while the installed local binding rejects it: TypeError: bead_search() got an unexpected keyword argument 'regex'. Focused reproduction: .venv/bin/python -m pytest tests/test_bead/test_cli_search.py::test_handle_bead_search_regex_matches_when_literal_cannot -q -vv fails with that TypeError. This matches the active published-binding-floor work on this epic; no standalone task bead created.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-i1.4.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-i1.4.land/README.md) | [sase-i1.4](sase-i1.4.md) | 0 |
