# Bead: sase-s1.1 — Ship the source-built xprompt LSP to every CI consumer

[Bead Pages](../README.md) / [sase-s1](README.md) / sase-s1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0al](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0al.md) · **Assignee:** `sase-s1.1` · **Size:** medium
**Created:** 2026-08-22 12:30:19 UTC · **Closed:** 2026-08-22 13:17:43 UTC
**Plan:** [202608/restore\_github\_actions.md](https://github.com/sase-org/sase--plans/blob/main/202608/restore_github_actions.md)

## Description

ci-runtime-artifacts: build, publish, install, and contract-test the xprompt LSP beside the Rust wheel from the same sase-core revision.

## Notes

[2026-08-22T12:54:58Z · sase-s1.1] PROPOSED FOLLOW-UP: SASE validation reports home memory/provider shims out of sync — just check fails at init memory --check wanting chezmoi memory/provider shim regeneration outside this phase scope.

[2026-08-22T13:06:03Z · sase-s1.1] PROPOSED FOLLOW-UP: The escalated full test lane fails tests/main/test_skills_handler.py::test_skills_inventory_reports_retired_deletion_drift — this matches the epic plan portable-cli-contracts Rich/path wrapping issue and currently blocks a clean full-suite lane.

[2026-08-22T13:17:43Z · sase-s1.1] Implemented CI LSP artifact build and setup-action install/probe contract; verified no epic-symbol leftovers, .venv/bin/sase-xprompt-lsp --version 0.29.13, pytest tests/test_github_actions_ci.py, pytest tests/test_xprompt_directive_completion_parity.py tests/test_xprompt_finalizer_completion_parity.py, and git diff --check. just check was run and clears through lint/toobig, then fails at out-of-scope init memory --check home memory drift; just test-scoped escalated to full suite and only fails the known portable-cli-contracts Rich/path wrapping test.

## Dependencies

- **Blocks:** [sase-s1.6](sase-s1.6.md) ◐ · ⧖ 2026-08-22

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s1.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s1.1/README.md) | [sase-s1.1](sase-s1.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fd1e42e`](https://github.com/sase-org/sase/commit/fd1e42e972918b3b64329083bf9484f921f560f5) | ci: ship xprompt lsp core artifact | [sase-s1.1](sase-s1.1.md) | 2026-08-22 13:19:09 UTC |
