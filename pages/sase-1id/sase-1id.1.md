# Bead: sase-1id.1 — Fail-closed %auto grammar in sase-core and Python

[Bead Pages](../README.md) / [sase-1id](README.md) / sase-1id.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0yg](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0yg.md) · **Assignee:** `sase-1id.1` · **Size:** medium
**Created:** 2026-10-08 13:39:30 EDT · **Closed:** 2026-10-08 14:58:37 EDT
**Plan:** [202610/auto\_p0\_safety\_tales.md](https://github.com/sase-org/sase--plans/blob/main/202610/auto_p0_safety_tales.md)

## Description

grammar: add one sase-core classifier for %auto spellings and use it in the Rust typed launch extractor, editor metadata, editor/LSP diagnostics, and the Python extractor, so named arguments, parenthesized forms, extra positionals, and unknown colon values fail at launch, and :manual/:off mean Manual. Commit sase-core and sase in the same turn so the host moves the core pin. Close task bead sase-1hg when done.

## Notes

[2026-10-08T18:30:05Z · sase-1id.1] PROPOSED FOLLOW-UP: tests/test_plan_gates_execution.py::test_shared_host_executor_handles_feedback_rejection_and_races fails identically on the clean base tree (verified via git stash of src changes); option_results mismatch on feedback flow with no %auto involved, no duplicate task bead found

[2026-10-08T18:58:09Z · sase-1id.1--1] PROPOSED FOLLOW-UP: just check mypy gate fails on src/sase/completion/candidates/catalog_build.py:71 (import-not-found for sase_core_rs, file untouched by grammar phase) identically on clean base tree via git stash; no task bead found

[2026-10-08T18:58:15Z · sase-1id.1--1] PROPOSED FOLLOW-UP: sase-core check has 1 failure in crates/sase_core/tests/bead_read_parity.rs::event_store_supports_read_queries_without_legacy_projection (bead_doctor WARNING assertion, no %auto involvement) identically on clean base tree via git stash; no task bead found

[2026-10-08T18:58:37Z · sase-1id.1--1] Fail-closed %auto grammar done in sase-core and sase. sase check: 160 passed (auto_grammar_parity, directives_flags, directive_edit, macro_directive_completion_parity incl. LSP binary); sase-core lib: 215 agent_launch + 118 directive + 23 auto pass. Full just check blocked only by pre-existing base-identical failures recorded as PROPOSED FOLLOW-UPs: mypy import-not-found on catalog_build.py:71, plan_gates feedback-race test, sase-core bead_read_parity event_store test. Task bead sase-1hg closed; epic-symbols clean.

## Dependencies

- **Blocks:** [sase-1id.5](sase-1id.5.md) ◐ · ⧖ 2026-10-08
- **Blocks:** [sase-1id.6](sase-1id.6.md) ◐ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1id.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1id.1.md) | [sase-1id.1](sase-1id.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@e8606a5`](https://github.com/sase-org/sase-core/commit/e8606a564e4ddccbc4eb2369f4f32dd02ce8c3af) | feat(auto): fail-closed %auto grammar classifier in sase-core | [sase-1id.1](sase-1id.1.md) | 2026-10-08 14:59:54 EDT |
| sase | [`0ac86ad`](https://github.com/sase-org/sase/commit/0ac86ad40c5fb8a31ca2bed929200fb1534772d3) | feat(auto): fail-closed %auto grammar in Python extractor and metadata | [sase-1id.1](sase-1id.1.md) | 2026-10-08 15:04:17 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1id.1--1][1] | Need phase scope | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1id.1.md

<!-- sase:referenced-by:end -->
