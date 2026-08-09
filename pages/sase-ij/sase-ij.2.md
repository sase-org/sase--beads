# Bead: sase-ij.2 — Build the window ratchet tool

[Bead Pages](../README.md) / [sase-ij](README.md) / sase-ij.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wq/README.md) · **Assignee:** `sase-ij.2` · **Size:** medium
**Created:** 2026-08-09 15:18:09 EDT · **Closed:** 2026-08-09 16:13:08 EDT
**Plan:** [202608/core\_window\_ratchet.md](https://github.com/sase-org/sase--plans/blob/main/202608/core_window_ratchet.md)

## Description

ratchet-tool: add a stdlib-only tools/ratchet_core_window that selects the newest fully published stable sase-core-rs from PyPI, rewrites only that requirement in pyproject.toml through one tested ceiling-policy function, refreshes uv.lock with a bounded diff guard, and supports --check/--report-only with idempotence and downgrade refusal.

## Notes

[2026-08-09T19:51:26Z · sase-ij.2] PROPOSED FOLLOW-UP: Fix Markdown formatting in sase/memory/build_and_run.md — just check currently stops at fmt-md-check because Prettier reports that memory file as unformatted; memory edits require explicit owner permission.

[2026-08-09T20:12:08Z · sase-ij.2] PROPOSED FOLLOW-UP: Investigate unrelated full non-visual suite failures during Justfile-triggered test-scoped escalation — after fixing the contract manifest, the earlier full run still showed ACE/TUI failures such as AcePage._wait_for_screen missing, onboarding/footer/navigation assertions, and tasks-pane cache behavior before manual interrupt at 17m19s.

[2026-08-09T20:13:08Z · sase-ij.2] Implemented tools/ratchet_core_window, Justfile recipe, tests, and contract manifest entry. Verified targeted pytest for the ratchet tool plus contract manifest, just _lint-pyscripts, just _lint-ruff, git diff --check, and just ratchet-core-window --report-only against PyPI. just check was attempted after the manifest fix and is blocked before tests by pre-existing fmt-md-check on sase/memory/build_and_run.md; proposed follow-ups recorded for that and unrelated full-lane failures.

[2026-08-09T20:14:45Z · sase-ij.2] Verified pytest tests/test_ratchet_core_window_tool.py tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection -q, just _lint-pyscripts, just _lint-ruff, git diff --check, and just ratchet-core-window --report-only; just check remained blocked by unrelated fmt-md-check failure in sase/memory/build_and_run.md.

## Dependencies

- **Depends on:** [sase-ij.1](sase-ij.1.md) ✓ · ⧖ 2026-08-09
- **Blocks:** [sase-ij.4](sase-ij.4.md) ◐ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ij.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.2/README.md) | [sase-ij.2](sase-ij.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ca2dbcb`](https://github.com/sase-org/sase/commit/ca2dbcb0fd8d4fee7a9df8f449a943a5683f8d70) | feat: add core window ratchet tool | [sase-ij.2](sase-ij.2.md) | 2026-08-09 16:15:34 EDT |
