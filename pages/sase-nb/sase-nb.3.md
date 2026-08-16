# Bead: sase-nb.3 — Flag beads in the Python bead layer

[Bead Pages](../README.md) / [sase-nb](README.md) / sase-nb.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03v](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03v.md) · **Assignee:** `sase-nb.3` · **Size:** medium
**Created:** 2026-08-16 12:24:52 EDT · **Closed:** 2026-08-16 14:49:19 EDT
**Plan:** [202608/feature\_flags.md](https://github.com/sase-org/sase--plans/blob/main/202608/feature_flags.md)

## Description

bead: mirror IssueType.FLAG and FlagRecord through the Python model, the SQLite compatibility layer, the wire conversion, and the sase bead create/show/update surfaces.

## Notes

[2026-08-16T18:48:01Z · sase-nb.3] PROPOSED FOLLOW-UP: tests/main/test_var_integration.py::test_var_cli_end_to_end_refreshes_index_and_round_trips_machine_outputs fails on master before any of this bead's changes (confirmed via git stash) — it hardcodes AGENT_ARTIFACT_INDEX_SCHEMA_VERSION - 1 as the pre-upgrade value and asserts the post-upgrade value equals the current constant, so any future schema-version bump without updating this test's literal breaks it; currently observed as 21 -> 22. Unrelated to the flag bead type work.

[2026-08-16T18:49:19Z · sase-nb.3] Mirrored IssueType.FLAG/FlagRecord through the Python model (bead/model.py), SQLite compat layer (_db_codec/_db_rows/_db_schema/_db_migrations), wire conversion (core/bead_wire.py), JSONL (bead/jsonl.py), mutation facades (core/bead_mutation_facade.py, bead/_project_mutations.py), and the CLI create/show/update/list surfaces (bead/cli_crud.py, cli_detail.py, cli_detail_json.py, main/parser_bead_lifecycle.py, main/parser_bead_queries.py), plus the shared flag_removal_due predicate (bead/flag_due.py) and flag_codec.py. Registered minimal BEAD_TYPE_PRESENTATIONS/BEAD_TYPE_NOUNS entries (using the look phase's exact glyph/accent values) since sase bead list/show crashed on any flag bead without them. Verified: full just check passed — every lint gate (fmt, ruff, mypy, pyscripts, test waits, changelog, terminology, symvision, toobig, SASE validation, committed plans) green; the diff-scoped test lane escalated to the full suite (rule: core-identity-changed) and ran 8949 passed, 4 skipped, with only tests/main/test_var_integration.py::test_var_cli_end_to_end_refreshes_index_and_round_trips_machine_outputs failing — confirmed via git stash to fail identically on unmodified master, so pre-existing and unrelated (recorded as a PROPOSED FOLLOW-UP note). Also fixed two ACE filter-bar type-completion tests and their static hint strings (profiles.py, bead_filter_bar.py) that widened once flag joined BEAD_TYPE_VALUES. Manual CLI smoke test confirmed create -> list -> show -> update --remove-by -> close round-trips end to end, and all validation-rule error messages match the core's text.

## Dependencies

- **Depends on:** [sase-nb.1](sase-nb.1.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-nb.4](sase-nb.4.md) ✓ · ⧖ 2026-08-16
- **Blocks:** [sase-nb.5](sase-nb.5.md) ✓ · ⧖ 2026-08-16

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-nb.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-nb.3/README.md) | [sase-nb.3](sase-nb.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e38d7b8`](https://github.com/sase-org/sase/commit/e38d7b80f7845abc53ff8c8b5e364248834ad1b5) | feat(bead): add flag issue type to the Python bead layer | [sase-nb.3](sase-nb.3.md) | 2026-08-16 14:50:45 EDT |
