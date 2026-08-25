# Bead: sase-th.2 — Refresh the bead CLI note fixtures and assertions

[Bead Pages](../README.md) / [sase-th](README.md) / sase-th.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0d8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0d8.md) · **Assignee:** `sase-th.2` · **Size:** small
**Created:** 2026-08-25 07:32:00 EDT · **Closed:** 2026-08-25 07:57:43 EDT
**Plan:** [202608/repair\_red\_master\_ci.md](https://github.com/sase-org/sase--plans/blob/main/202608/repair_red_master_ci.md)

## Description

bead-notes: regenerate the six bead CLI goldens for the structured-note wire, retarget the compact-search assertion, and replace the hardcoded history date literal with a computed one.

## Notes

[2026-08-25T11:57:43Z · sase-th.2] Verified bead CLI structured-note fixture refresh with .venv/bin/pytest tests/test_bead/test_cli_golden.py -q (40 passed) and .venv/bin/pytest tests/test_bead/test_cli_search.py::test_handle_bead_search_compact_includes_closed_and_match_reason tests/test_bead/test_cli_history.py::test_history_full_makes_overwritten_note_revisions_readable -q (2 passed). Ran sase bead epic-symbols sase-th.2: no entries. Ran just check; it passed fmt/ruff/mypy and earlier lint gates, then stopped at the known sibling symvision failures assigned to sase-th.1.

## Dependencies

- **Blocks:** [sase-th.7](sase-th.7.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-th.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-th.2/README.md) | [sase-th.2](sase-th.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`436baa7`](https://github.com/sase-org/sase/commit/436baa7c1770d2b05cc471e8032424d86bec8999) | test(beads): refresh structured note CLI fixtures | [sase-th.2](sase-th.2.md) | 2026-08-25 07:58:45 EDT |
