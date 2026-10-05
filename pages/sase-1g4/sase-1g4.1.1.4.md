# Bead: sase-1g4.1.1.4 — Schemas, doctor check, dogfood enums, and docs

[Bead Pages](../README.md) / [sase-1g4.1.1](sase-1g4.1.1.md) / sase-1g4.1.1.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1g4.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.1.md) · **Assignee:** `sase-1g4.1.1.4` · **Size:** medium
**Created:** 2026-10-04 18:33:20 EDT · **Closed:** 2026-10-04 22:55:46 EDT
**Plan:** [202610/macro\_input\_type\_vocab.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_input_type_vocab.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | [bead:sase-1gg][1] | Proposing phase note #2 |
| related | [bead:sase-1gh][2] | Proposing phase note #5 |
| related | [bead:sase-1gi][3] | Proposing phase note #6 |

_Plus 1 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1gg/README.md
[2]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1gh/README.md
[3]: https://github.com/sase-org/sase--beads/blob/main/pages/sase-1gi/README.md

<!-- sase:links:end -->

## Description

surface: generate the macro input JSON schemas, add the config.macro_input_types doctor check, make #pr status an enum, and document the value rules.

## Notes

[2026-10-05T02:01:03Z · sase-1g4.1.1.4] PROPOSED FOLLOW-UP: Resume remaining loader integration from sase-1g4.1.1.3 (flag bead sase-1g9) — parse_input_type adapter over resolve_input_type, InputChoice.description, named_type/value_role, validate_enum_choices at load, isolation, and handoff. Surface wired longform workflow choices so #pr could load; the rest is still un-wired.

[2026-10-05T02:55:18Z · sase-1g4.1.1.4--3] PROPOSED FOLLOW-UP: test_cancel_saves_once_submit_path_quiet FrontmatterPanel NoMatches(#frontmatter-raw) under 14-worker just check — ToolRun d1031947d02a0922a64213d8bde089ef; isolation pytest passed (3.64s call). Same missing-widget symptom as sase-1fy/sase-1g5, different node. Related flake-class epic sase-j7.

[2026-10-05T02:55:46Z · sase-1g4.1.1.4--3] Surface schemas, doctor check, #pr enum, and docs are in. tools/sync_macro_input_schemas --check, sase doctor -C config.macro_input_types (OK on bundled macros), and 83 targeted tests passed (test_pr_status_enum, test_macro_input_schemas, test_macro_input_type_parity, test_checks_config_macro_input_types, loader/model tests). #pr(x, status=ready) binds; status=Ready suggests ready; #pr:ready binds name. just check ToolRun d1031947d02a0922a64213d8bde089ef failed two NEW ACE TUI nodes: test_prompt_source_token_changes_for_project_file reproduced on clean HEAD 25cc3c475d and is already fixed by origin 404b0e2ac2 (sase-1eq.5.1.6); test_cancel_saves_once_submit_path_quiet passed in isolation and is recorded as PROPOSED FOLLOW-UP (sase-1fy/sase-1g5 class, sase-j7). No leftover --epic-symbol entries.

[2026-10-05T03:26:22Z · sase-1g4.1.1.4--4] Pinned test_mini_macro_target_catalog.py xprompt string literals in the terminology allowlist. test_macro_string_literals_avoid_xprompt_terms failed on clean HEAD 404b0e2ac2 (3 strings: legacy_xprompt_syntax_enabled plus two xprompts config-key fixtures); not caused by surface schemas. Allowlist + classified reason added so just check can land.

[2026-10-05T03:55:03Z · sase-1g4.1.1.4--5] PROPOSED FOLLOW-UP: test_sudo_runner_invocation_keeps_canary_out_of_process_argv_and_env flakes under 14-worker just check — ToolRun 5f4761a962676903e627a36a4d0b5365; isolation pytest passed (0.34s call). AssertionError: credential length leaked into process metadata (canary length 8119 in /proc environ). Sibling node sase-19d; flake-class epic sase-j7.

[2026-10-05T03:55:07Z · sase-1g4.1.1.4--5] PROPOSED FOLLOW-UP: test_agent_run_stops_on_a_new_item flakes under 14-worker just check — ToolRun 5f4761a962676903e627a36a4d0b5365; isolation pytest passed (0.77s call). Nested simulated mypy output src/unique.py:9 never-seen-before leaked into parent extractor as NEW; nested run stopped with helper_error instead of new_item/unknown_item. Related closed sase-114; flake-class epic sase-j7.

[2026-10-05T03:55:39Z · sase-1g4.1.1.4--5] Surface schemas, doctor check, #pr enum, and docs verified; just check NEW items were isolation-passing full-lane flakes recorded as PROPOSED FOLLOW-UP

[2026-10-05T03:55:43Z · sase-1g4.1.1.4--5] Surface schemas, doctor check, #pr enum, and docs remain in. tools/sync_macro_input_schemas --check, workspace sase doctor -C config.macro_input_types (OK on bundled macros), and 84 targeted tests passed after just fix. Isolation pytest of the two just-check NEW nodes passed. unique.py mypy item is nested fixture output, not a source file. No leftover --epic-symbol entries. just check ToolRun 5f4761a962676903e627a36a4d0b5365 failed two isolation-passing full-lane flakes recorded as PROPOSED FOLLOW-UP (sase-19d/sase-114 class, sase-j7).

## Dependencies

- **Depends on:** [sase-1g4.1.1.2](sase-1g4.1.1.2.md) ✓ · ⧖ 2026-10-04
- **Depends on:** [sase-1g4.1.1.3](sase-1g4.1.1.3.md) ✓ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.1.1.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.1.1.4.md) | [sase-1g4.1.1.4](sase-1g4.1.1.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2a55a03`](https://github.com/sase-org/sase/commit/2a55a03deb48f86f002ae6cde3025ec8459df74b) | feat(macros): generate input-type schemas and dogfood #pr status enum | [sase-1g4.1.1.4](sase-1g4.1.1.4.md) | 2026-10-05 01:02:47 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1g4.1.1.4--5][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.1.1.4.md

<!-- sase:referenced-by:end -->
