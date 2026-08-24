# Bead: sase-sq.3 — Selector-based memory read and the web command group

[Bead Pages](../README.md) / [sase-sq](README.md) / sase-sq.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0cb](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0cb.md) · **Assignee:** `sase-sq.3` · **Size:** medium
**Created:** 2026-08-24 09:32:15 EDT · **Closed:** 2026-08-24 15:10:29 EDT
**Plan:** [202608/memory\_webs.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_webs.md)

## Description

cli: make `sase memory read`/`show` variadic over note, web, and web:keyword selectors, add `sase memory web list|show`, and unify the read audit event around a note/web/strand kind discriminator.

## Notes

[2026-08-24T19:09:09Z · sase-sq.3] PROPOSED FOLLOW-UP: tests/test_config_schema.py::test_default_config_matches_public_schema fails on master — default_config.yml sets finalizers.instances.commit.refusal to 'defer' but the public JSON schema only allows 'fail'; confirmed pre-existing via git stash, unrelated to this phase.

[2026-08-24T19:09:32Z · sase-sq.3] PROPOSED FOLLOW-UP: tests/test_vcs_log_filter_query.py::test_canonical_query_round_trip_property is flaky — Hypothesis FailedHealthCheck (input generation too slow); confirmed pre-existing via git stash, unrelated to this phase.

[2026-08-24T19:09:50Z · sase-sq.3] PROPOSED FOLLOW-UP: tests/doctor/test_checks_beads.py::test_project_beads_skips_when_store_is_absent fails on master (expects status SKIP, gets OK); confirmed pre-existing via git stash, unrelated to this phase.

[2026-08-24T19:10:29Z · sase-sq.3] Implemented: sase memory read/show now variadic over note/web/web:keyword selectors with -d/--depth and -p/--project, atomic batch resolution (one bad selector = no output, no audit write); new sase memory web list/show command group (bare 'memory web' delegates to list); sase memory list gained a webs panel; READ_LOG_SCHEMA_VERSION bumped to 2 with an additive kind:note|web|strand discriminator (selectors/resolved_targets/included_targets/depth/scope_origin) while keeping v1 rows and existing single-note consumers byte-identical; sase memory log --include glossary folds in legacy glossary_reads.jsonl. Strand mention-closure reuses resolve_glossary_closure via a new sase.memory.web.closure bridge, verified end-to-end in a sandbox project (closure:none vs closure:mentions). Added ~30 new tests (selector batch resolution, CLI atomicity/mixed-batch/core-descriptor-refused-strand-allowed, web list/show, v1/v2 read_log round-trip, --include glossary) plus updated existing tests broken by the memory_path->selectors rename; regenerated the completion CLI spec snapshot. just lint and just check both pass; check's scoped test lane hit 2 pre-existing unrelated failures (config schema 'defer' refusal choice, a flaky hypothesis test) confirmed via git-stash comparison and logged as follow-ups, plus one pre-existing unrelated doctor test failure. No epic-symbol entries for this phase.

## Dependencies

- **Depends on:** [sase-sq.2](sase-sq.2.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-sq.4](sase-sq.4.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-sq.5](sase-sq.5.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sq.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sq.3/README.md) | [sase-sq.3](sase-sq.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`cbda792`](https://github.com/sase-org/sase/commit/cbda7926f05ffc09eb1c3aaa4693f4fe6a1fbda7) | feat(memory): make memory read/show variadic over note/web/strand selectors and add the web command group | [sase-sq.3](sase-sq.3.md) | 2026-08-24 15:12:12 EDT |
