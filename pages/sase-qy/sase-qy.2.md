# Bead: sase-qy.2 — Persistent query bar on Bead and File

[Bead Pages](../README.md) / [sase-qy](README.md) / sase-qy.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.07r](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.07r.md) · **Assignee:** `sase-qy.2` · **Size:** medium
**Created:** 2026-08-19 10:02:24 EDT · **Closed:** 2026-08-19 12:48:01 EDT
**Plan:** [202608/artifacts\_persistent\_query\_bar.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifacts_persistent_query_bar.md)

## Description

panes: make BeadFilterBar and FileFilterBar persistent, add a single `_sync_query_bar` funnel that keeps each idle bar's text and status truthful, and stop echoing the active query as chips in those panes' identity headers.

## Notes

[2026-08-19T16:47:07Z · sase-qy.2] PROPOSED FOLLOW-UP: Justfile symvision --epic-symbol list has 13 stale entries for closed beads sase-qt.6 and sase-qt.7 (MemoryConflictError, MemoryDraftValidation, etc., MemoryPanel), causing `just check`/`just _lint-symvision` to fail red on clean master. Confirmed pre-existing via git stash test, unrelated to sase-qy.2. Needs the entries removed or re-keyed per the epic-symbol staleness rule.

[2026-08-19T16:47:24Z · sase-qy.2] PROPOSED FOLLOW-UP: `sase validate` fails its `init memory --check` step on clean master (15 memory files/provider shims out of sync, e.g. sase/memory/task_types.md, AGENTS.md, CLAUDE.md, GEMINI.md, QWEN.md, OPENCODE.md). Confirmed pre-existing via git stash test, unrelated to sase-qy.2. Memory file edits require explicit user permission so this was left untouched.

[2026-08-19T16:47:40Z · sase-qy.2] PROPOSED FOLLOW-UP: tests/completion/test_snapshot.py::test_checked_in_snapshot_has_no_drift and test_current_structural_view_matches_checked_in_snapshot fail on clean master — checked-in CLI completion spec is out of sync with the argparse tree (`just sync-completion-spec` needed). Confirmed pre-existing via git stash test, unrelated to sase-qy.2.

[2026-08-19T16:48:01Z · sase-qy.2] Verified: ruff and mypy clean on all changed files; 648 targeted pytest tests (full artifacts + filter_bar surface, including the two new BeadFilterBar submit/idle-sync tests) pass; just check gates all pass except lint(symvision), validate(init memory), and test-scoped's completion-snapshot drift, all three confirmed pre-existing/unrelated via git stash. Fixed an invalid 'type:epic' test query (should be 'tier:epic', since epic is a bead tier not a type) discovered while diagnosing a test hang. No --epic-symbol entries for this phase.

## Dependencies

- **Depends on:** [sase-qy.1](sase-qy.1.md) ✓ · ⧖ 2026-08-19
- **Blocks:** [sase-qy.3](sase-qy.3.md) ✓ · ⧖ 2026-08-19

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qy.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qy.2/README.md) | [sase-qy.2](sase-qy.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1a0d8e8`](https://github.com/sase-org/sase/commit/1a0d8e867184c87c4bf39ac798378ea64bb6b978) | feat(ace): make BeadFilterBar and FileFilterBar persistent | [sase-qy.2](sase-qy.2.md) | 2026-08-19 12:48:50 EDT |
