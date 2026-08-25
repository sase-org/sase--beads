# Bead: sase-t8.3 — Expose shell forks throughout ACE

[Bead Pages](../README.md) / [sase-t8](README.md) / sase-t8.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0cz.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0cz.f1.md) · **Assignee:** `sase-t8.3` · **Size:** medium
**Created:** 2026-08-24 18:28:19 EDT · **Closed:** 2026-08-24 21:15:43 EDT
**Plan:** [202608/fork\_every\_shell.md](https://github.com/sase-org/sase--plans/blob/main/202608/fork_every_shell.md)

## Description

shell-surfaces: enable F and completion for every shell row, document the behavior, and verify the complete workflow.

## Notes

[2026-08-25T01:15:19Z · sase-t8.3--1] PROPOSED FOLLOW-UP: 8 pre-existing just test failures unrelated to this phase — tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[list_full|list_json|list_json_limit|list_implicit_closed_json|show_json|show_phase_json], tests/test_bead/test_cli_history.py::test_history_full_makes_overwritten_note_revisions_readable, tests/test_bead/test_cli_search.py::test_handle_bead_search_compact_includes_closed_and_match_reason. Confirmed by git-stashing this phase's changes and rerunning: all 8 fail identically on clean tree at HEAD. Golden fixtures expect old notes/NOTES output shape; actual output now differs (e.g. "notes": "" vs "notes": [] + notes_text, "NOTES" vs "NOTES (1)"), consistent with the notes-shape change from commit 37c8e303a (refactor(bead): split _project_mutations.py into per-concern submixins) — the same commit already flagged as breaking the just lint symvision gate. Golden fixtures under tests/test_bead/ likely need regenerating for the new notes shape.

[2026-08-25T01:15:43Z · sase-t8.3--1] Full just test suite run (36957 passed, 13 skipped, 8 failed in 934.75s). All 8 failures confirmed pre-existing and unrelated to this phase: verified by git-stashing this phase's changes and rerunning the 8 failing tests (tests/test_bead/test_cli_golden.py x6, test_cli_history.py x1, test_cli_search.py x1) against clean HEAD — identical failures reproduce with none of this phase's changes present. Root cause is unrelated bead-refactor commit 37c8e303a changing bead notes output shape (same commit already known to break just lint's symvision gate). This phase's own changes (shell-fork exposure across resolve_agent_prompt_target_scope, keybinding footer, command availability, completion candidates, docs, fork.yml xprompt) verified separately: ruff and mypy pass, and the 172 directly-touched tests in tests/test_keybinding_footer_agent.py, tests/test_command_availability_agents.py, tests/ace/tui/test_agent_wait_resume_targets.py, tests/ace/tui/test_agent_completion.py all pass. No --epic-symbol leftovers for this phase (sase bead epic-symbols sase-t8.3 reported none). Filed a PROPOSED FOLLOW-UP note on this bead for the pre-existing golden-fixture breakage.

## Dependencies

- **Depends on:** [sase-t8.1](sase-t8.1.md) ✓ · ⧖ 2026-08-24
- **Depends on:** [sase-t8.2](sase-t8.2.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-t8.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-t8.3.md) | [sase-t8.3](sase-t8.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`69dc50a`](https://github.com/sase-org/sase/commit/69dc50a31af35724d9784b775f557fad3ea0a57f) | feat(ace): expose shell forks throughout ACE | [sase-t8.3](sase-t8.3.md) | 2026-08-24 21:16:35 EDT |
