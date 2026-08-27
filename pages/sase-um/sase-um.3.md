# Bead: sase-um.3 — Scheduled heavy lane off the push path

[Bead Pages](../README.md) / [sase-um](README.md) / sase-um.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ek](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ek.md) · **Assignee:** `sase-um.3` · **Size:** medium
**Created:** 2026-08-26 19:12:25 EDT · **Closed:** 2026-08-27 08:28:27 EDT
**Plan:** [202608/release\_gate\_liveness.md](https://github.com/sase-org/sase--plans/blob/main/202608/release_gate_liveness.md)

## Description

heavy: make ci.yml pull-request-and-workflow_call only, add full.yml as a scheduled caller carrying the exhaustive matrix, retire the flake-reproducer cron from the master push path, repoint the coverage-contexts consumer, and add the second README badge.

## Notes

[2026-08-27T12:27:25Z · sase-um.3] PROPOSED FOLLOW-UP: Persistent ACE artifact relation collapse failures - just check escalated to the full suite and failed tests/ace/tui/test_artifacts_relation_collapse.py::test_expanded_link_row_renders_edge_metadata plus ::test_dot_collapses_and_expands_on_each_relations_pane; both fail when rerun directly and are outside the workflow changes.

[2026-08-27T12:27:52Z · sase-um.3] PROPOSED FOLLOW-UP: just install LSP install reports success after copy errors - during this phase, just install emitted cp/chmod/mv errors for sase-xprompt-lsp, exited 0, and .venv/bin/sase-xprompt-lsp --version reported 0.32.6 after building sase_core_rs 0.32.8.

[2026-08-27T12:28:27Z · sase-um.3] Implemented CI split: ci.yml is pull_request/workflow_call only, full.yml schedules/calls it every 2h, coverage-contexts fetcher now targets full.yml, docs/README/tests updated. Verified epic-symbols empty; focused workflow/layout tests passed (85 passed). just check ran and failed only in persistent unrelated ACE artifact relation collapse tests recorded as PROPOSED FOLLOW-UP; full.yml has no remote run yet, so real artifact fetch is not possible before this workflow lands.

## Dependencies

- **Depends on:** [sase-um.1](sase-um.1.md) ✓ · ⧖ 2026-08-26
- **Blocks:** [sase-um.6](sase-um.6.md) ◐ · ⧖ 2026-08-26
- **Blocks:** [sase-um.7](sase-um.7.md) ◐ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.3/README.md) | [sase-um.3](sase-um.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`840dd3e`](https://github.com/sase-org/sase/commit/840dd3eb4af4c5c93f4806ef00b31fad3ce02758) | ci: move exhaustive workflow to scheduled full lane | [sase-um.3](sase-um.3.md) | 2026-08-27 08:29:47 EDT |
