# Bead: sase-x8.1 — Add a batched Rust query for waited producers' artifact metadata

[Bead Pages](../README.md) / [sase-x8](README.md) / sase-x8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gj.f0.f0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gj.f0.f0.md) · **Assignee:** `sase-x8.1` · **Size:** medium
**Created:** 2026-09-05 19:26:20 EDT · **Closed:** 2026-09-05 20:26:22 EDT
**Plan:** [202609/wait\_artifacts.md](https://github.com/sase-org/sase--plans/blob/main/202609/wait_artifacts.md)

## Description

artifact-query: implement the exact-producer metadata contract in Rust, its Python binding and thin adapter, and isolation tests.

## Notes

[2026-09-06T00:25:52Z · sase-x8.1] PROPOSED FOLLOW-UP: full just check runs (2x, ~39K tests, unrelated to this diff) intermittently failed 6 tests unconnected to artifact-context work: tests/test_axe_default_chop_triggers.py::test_artifact_glob_chops_skip_idle_and_fire_on_new_agent_artifact (bead_claim_checks/wait_checks params, different subset each run), tests/main/test_init_onboarding_parser.py::test_init_help_lists_existing_subcommands (fails deterministically even in isolation on unmodified master — argparse --help text missing "-p NAME, --project NAME", looks like terminal-width/COLUMNS-dependent wrapping), and 3-4 of tests/ace/tui/widgets/test_prompt_panel_section_navigation_targets.py (pass individually in isolation, fail only under the full parallel suite). None of the failing files reference artifact_context; verified by git-stashing this diff and re-running the same tests in isolation on unmodified master (5/6 passed, 1/6 failed identically). Worth a flake-type bead investigation.

[2026-09-06T00:26:22Z · sase-x8.1] Implemented the exact-producer artifact-context contract in sase-core (crates/sase_core/src/artifact_file/context.rs: query_artifact_context + ArtifactContextProducerGroupWire/ArtifactContextEntryWire, wire schema v1, index read at most once and only for a nonempty batch, exact agent_artifacts_dir matching, chat exclusion, dependency/producer/creation-time ordering, first-dependency dedup) plus its PyO3 binding (artifact_context_query / artifact_context_query_wire_schema_version) and a thin Python facade (src/sase/core/artifact_context_query_facade.py). Verified: sase-core — cargo fmt/clippy -D warnings/full workspace test all green (2046+105 tests incl. 12 new Rust unit tests + 1 new pyo3 binding test), confirmed via git-stash that the pre-existing libpython3.14 dlopen issue and everything else is unaffected by this change. sase repo — added tests/test_artifact_context_query_facade.py (12 tests incl. real end-to-end binding round trips for exact-producer matching, chat exclusion, dependency-order+dedup, and empty-batch no-index-access) plus symvision --epic-symbol entries keyed to the still-open parent epic sase-x8 for the two facade symbols phase sase-x8.2 will consume. just check is green except 6 pre-existing, unrelated test failures (chop-trigger/argparse-help/TUI-prompt-panel tests with no reference to artifact_context) reproduced identically on unmodified master and recorded as a PROPOSED FOLLOW-UP note. No --epic-symbol entries remain keyed to sase-x8.1 (sase bead epic-symbols confirmed clean).

## Dependencies

- **Blocks:** [sase-x8.2](sase-x8.2.md) ◐ · ⧖ 2026-09-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x8.1/README.md) | [sase-x8.1](sase-x8.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d64696c`](https://github.com/sase-org/sase/commit/d64696cce522d9a7a13f4304ac650c86d45be334) | feat(core): add exact-producer artifact-context query facade | [sase-x8.1](sase-x8.1.md) | 2026-09-05 20:30:14 EDT |
