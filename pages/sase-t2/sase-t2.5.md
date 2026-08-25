# Bead: sase-t2.5 — Note edit and retraction

[Bead Pages](../README.md) / [sase-t2](README.md) / sase-t2.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ct](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ct.md) · **Assignee:** `sase-t2.5` · **Size:** medium
**Created:** 2026-08-24 14:37:58 EDT · **Closed:** 2026-08-25 08:34:20 EDT
**Plan:** [202608/timestamped\_bead\_notes.md](https://github.com/sase-org/sase--plans/blob/main/202608/timestamped_bead_notes.md)

## Description

repair: add `sase bead note --edit` and `--remove` with their own events, an `edited` render marker, and drop the clobbering Notes field from the ACE bead editor modal.

## Notes

[2026-08-25T12:30:16Z · sase-t2.5] PROPOSED FOLLOW-UP: just check symvision gate fails on master (unrelated to this phase) — 10 unused public glossary/memory symbols left behind by commit cebab38a1 "feat(memory): retire config glossary infrastructure" (GlossaryReadAgentSummary/GlossaryReadError/GlossaryReadTermSummary/summarize_glossary_reads_by_agent/summarize_glossary_reads_by_term in legacy_glossary_read_log.py, build_relation_chip_rows in glossary_preview_render.py, filter_glossary_entries in web/text_filter.py, fsync_directory in atomic_write.py, render_glossary_catalog/render_glossary_closure in web/render.py) — need to be made private or deleted.

[2026-08-25T12:30:38Z · sase-t2.5] PROPOSED FOLLOW-UP: tests/sdd_store/test_sidecar_clone.py::test_sidecar_clone_retries_transient_transport_failures fails on master (unrelated to this phase) — it monkeypatches sase.sdd._store_link.time.sleep, but commit 51f6369b3 "refactor(sdd): split store-link clone helpers" moved that usage out of _store_link.py, so the module no longer has a time attribute to patch; test needs to target the new location.

[2026-08-25T12:31:01Z · sase-t2.5] PROPOSED FOLLOW-UP: tests/test_bead/test_cli_history.py::test_history_full_makes_overwritten_note_revisions_readable fails on master (unrelated to this phase) — it asserts a hardcoded literal date `"from: [2026-08-24"`, but `_revision_chain()` calls `project.create(..., notes=...)` without freezing time, so the recorded note timestamp is whatever day the suite actually runs on; the assertion silently breaks once "today" advances past the hardcoded date. Needs to freeze/monkeypatch `_now()` or compute the expected date dynamically.

[2026-08-25T12:31:25Z · sase-t2.5] PROPOSED FOLLOW-UP: tests/test_agent_artifact_marker_path_passing_audit.py::test_tracked_marker_path_passing_sites_are_reviewed fails on master (unrelated to this phase, confirmed on a clean stash) — it asserts an exact reviewed-sites allowlist that is missing 6 sites in src/sase/scripts/_agent_chat_from_name_{common,family,failure,resume}.py (e.g. resolve_meta_chat_path, completed_response_path, resolve_done_response_path, _resolve_family_member_resume_transcript, _resolve_agent_family_member_shell, _resolve_failed_agent_transcript); those sites need review and adding to _REVIEWED_PATH_PASSING_CONTEXTS.

[2026-08-25T12:34:20Z · sase-t2.5] Implemented sase bead note --edit/--remove for note edit and retraction. sase-core: added NoteEdited/NoteRemoved events + reducer arms (events.rs), edit_issue_note/remove_issue_note mutations that reject unknown note ids before writing any event and stamp edited_at/edited_by (mutation.rs), and bead_note_edit/bead_note_remove PyO3 bindings (sase_core_py/lib.rs); cargo test -p sase_core (1973+ tests) and -p sase_core_py (100 tests) pass, cargo fmt and cargo clippy -D warnings clean. Python: sase bead note gained mutually-exclusive -e/--edit N and -x/--remove N (N is the 1-based ordinal from sase bead show, resolved to a note id before mutating; out-of-range ordinals refuse without writing); new edit_note/remove_note on BeadProject and the mutation facade; note_edit/note_remove commit messages; removed the clobbering Notes field from the ACE bead editor modal (BeadEditorResult, compose(), changed_fields(), styles.tcss). bead_note_label already rendered the edited marker from an earlier phase, so no changes needed there. Verified with: sase-core cargo test/fmt/clippy; sase repo just check (fmt, ruff, mypy, keep-sorted, feature flags, pyscripts, test waits, changelog, patch/stitch terminology, validate, validate-committed-plans, toobig, and the diff-scoped test lane all green) plus a full tests/test_bead + tests/ace/tui/test_artifacts_beads_mutations.py + tests/completion run (2330 passed). Also regenerated the completion spec/mutex-group-count snapshot and 6 stale bead-notes-JSON golden CLI fixtures left out of sync by this epic's earlier show/pyapi phases, and fixed one stale test_cli_search.py assertion from the old flat-notes format — all confirmed pre-existing via a stash comparison before I touched them. Filed 4 PROPOSED FOLLOW-UP notes on this bead for pre-existing, unrelated breakage on master (confirmed via the same stash comparison, left unfixed as out of scope): the symvision unused-glossary-symbols lint gate, a sidecar-clone test broken by the prior _store_link split refactor, a bead-history test with a hardcoded literal date, and an agent-chat marker-path-passing audit allowlist gap. epic-symbols sase-t2.5 reports no --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-t2.3](sase-t2.3.md) ✓ · ⧖ 2026-08-24
- **Depends on:** [sase-t2.4](sase-t2.4.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-t2.6](sase-t2.6.md) ◐ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-t2.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-t2.5/README.md) | [sase-t2.5](sase-t2.5.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`868fa81`](https://github.com/sase-org/sase/commit/868fa81e1ac8df8de112608b769721b047290abb) | feat(bead): add sase bead note --edit/--remove for note edit and retraction | [sase-t2.5](sase-t2.5.md) | 2026-08-25 08:35:46 EDT |
| sase-core | [`sase-core@f06a103`](https://github.com/sase-org/sase-core/commit/f06a103287504c5348463e001f83a69654e99656) | feat(bead): add NoteEdited/NoteRemoved events and note edit/remove mutations | [sase-t2.5](sase-t2.5.md) | 2026-08-25 08:36:44 EDT |
