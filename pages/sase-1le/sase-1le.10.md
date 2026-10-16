# Bead: sase-1le.10 — Executable tutorial tests on fakey

[Bead Pages](../README.md) / [sase-1le](README.md) / sase-1le.10

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.research.4l.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.research.4l.linker.w0.md) · **Assignee:** `sase-1le.10` · **Size:** medium
**Created:** 2026-10-15 18:11:11 EDT · **Closed:** 2026-10-15 22:59:05 EDT
**Plan:** [202610/sase\_sh\_docs\_redesign.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_sh_docs_redesign.md)

## Description

tutorial-tests: run every marked shell block in start/ against fakey in a temporary HOME, and add the runner to the scheduled Full CI lane.

## Notes

[2026-10-16T02:58:39Z · sase-1le.10] Feasibility spike (tutorial-tests): fakey @ok via llm_provider.default_model=fakey-large in an isolated HOME (machine_name file + sase_<machine>.yml overlay) launches both +home tutorial runs to success; TUI-inspection steps have no headless equivalent so the runner asserts launch exit 0 then `sase agent wait NAME` settles 0 instead; runner scrubs SASE_AGENT*/ARTIFACTS/BEAD/PROMPT/TOOL/MONITOR/PROC/CHOP/JOB/LAUNCH context and overrides SASE_TMPDIR so tutorial shells behave as a fresh user.

[2026-10-16T02:58:47Z · sase-1le.10] PROPOSED FOLLOW-UP: just check stays red on the clean base tree via three failures sibling phases already triage — fmt-docs-check drift in docs/reference/glossary.md + design-decisions.md (see sase-1le.9 and sase-1le.16 notes, owned by sase-1le.8 pipeline), mypy errors in tools/render_cli, and docs-check strict warnings for dangling ../getting_started.md links from concepts/*.md (see sase-1le.13 note); none are touched by this phase.

[2026-10-16T02:58:52Z · sase-1le.10] PROPOSED FOLLOW-UP: Consider a demos/ VHS tape for tutorial 1 TUI step if the screenshot pipeline makes it cheap (plan-listed optional; skipped here because the interactive TUI step has no headless assertion).

[2026-10-16T02:59:05Z · sase-1le.10] Done: tests/test_tutorials.py runs every unskipped shell block in docs/start/ (nav order) in a temp HOME pinned to fakey-large, asserts exit codes + expect markers, waits each sase run to settled-success; just test-tutorials passes 5/5 (e2e 18s, both tutorial launches succeed); slow marker keeps fast lanes out; ci.yml tutorial-tests job runs it on the scheduled Full CI lane; writing-docs.md gains Testing the tutorials. Broken-step readability proven by unit tests. just check red only via three base-tree failures reproduced identically on stash (fmt-docs drift, render_cli mypy, getting_started links) recorded as follow-ups.

## Dependencies

- **Blocks:** [sase-1le.20](sase-1le.20.md) ◐ · ⧖ 2026-10-15
- **Depends on:** [sase-1le.9](sase-1le.9.md) ✓ · ⧖ 2026-10-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1le.10](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1le.10/README.md) | [sase-1le.10](sase-1le.10.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`82c595d`](https://github.com/sase-org/sase/commit/82c595d8400a5a52c70345b3afd56cd7f56d9ee1) | feat(tutorials): add tutorial test harness with Justfile recipe and CI job | [sase-1le.10](sase-1le.10.md) | 2026-10-15 23:00:54 EDT |
