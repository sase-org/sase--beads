# Bead: sase-uk.1 — The allocator and the scanner

[Bead Pages](../README.md) / [sase-uk](README.md) / sase-uk.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ej](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ej.md) · **Assignee:** `sase-uk.1` · **Size:** medium
**Created:** 2026-08-26 17:44:35 EDT · **Closed:** 2026-08-26 18:29:40 EDT
**Plan:** [202608/link\_traversing\_pager.md](https://github.com/sase-org/sase--plans/blob/main/202608/link_traversing_pager.md)

## Description

primitives: create the beta flag, extend `jump_hints` with prefix-free variable-width label allocation over a reserved-key alphabet, and add the one `link_scan` module that finds typed refs, URLs, paths, and origin-scoped bare tokens in plain text.

## Notes

[2026-08-26T22:28:08Z · sase-uk.1] PROPOSED FOLLOW-UP: pre-existing, unrelated tree drift blocks a fully green `just check`/`just check-full` right now — verified by stashing all sase-uk.1 changes and reproducing the same failures on bare master: `sase validate` (init memory --check) reports a stale `sase/artifact_relations.json`/`sase_artifacts.md`/README snapshot (missing `produced-by`/`launched` relation kinds), `tests/completion/test_snapshot.py` (both tests) and `tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection` report a stale completion-spec/contract-manifest snapshot, `tests/main/test_init_memory_committed_drift.py`, `tests/agent/test_pending_handoff.py::test_pending_handoff_markers_are_named_constants`, `tests/test_agent_artifact_marker_path_passing_audit.py`, and `tests/memory/test_memory_selector_render.py::test_note_section_retains_children_listing_beneath_its_header` also fail on bare master, and `tests/ace/tui/visual/test_ace_png_snapshots_agents_metadata_search.py` fails to even collect (imports a nonexistent `_zoom_agent` helper from `test_ace_png_snapshots_agents_zoom.py`). Root cause looks like the linked sase-core checkout running ahead of pyproject's compatibility window (noted by `just install`/`validate_sase_core_rs_version` as "no action needed" but apparently drifting generated snapshots). None of this touches jump_hints.py/link_scan.py/the feature-flag registry. Land agent should regenerate the stale snapshots (`sase memory init`, `just sync-completion-spec`, contract-manifest regen) and fix or delete the broken PNG-snapshot test import once the tree is not mid-epic.

[2026-08-26T22:28:32Z · sase-uk.1] PROPOSED FOLLOW-UP: two scope notes for later phases. (1) `PagerOrigin`, `LinkSpan`, `LinkSpanKind`, `scan_links`, `scan_bounded_links`, and `BoundedLinkScan` are defined in `src/sase/pager/link_scan.py` (re-exported from `src/sase/pager/__init__.py`) rather than in `document.py` — the `document` phase (sase-uk.2) should import `PagerOrigin` from here rather than redefining it, since D2 lists PagerOrigin as one of document.pys deliverables. (2) The BEAD-origin bare-token recognizer only matches this checkouts own `sase-` project-key prefix (`_BARE_BEAD_ID_RE` in link_scan.py) to avoid false positives on generic hyphenated prose; generalizing it to arbitrary bead-store project keys is deferred.

[2026-08-26T22:29:40Z · sase-uk.1] Created the beta link_pager feature flag (sase flag new + registry entry + schema sync, sase-ul removal bead). Extended build_jump_hint_maps in jump_hints.py with an opt-in prefix_free/excluded mode plus the PAGER_RESERVED_JUMP_COMMAND_KEYS constant; existing fixed-width callers are byte-for-byte unaffected (verified: their own test suite + a new explicit equivalence test). Added src/sase/pager/link_scan.py implementing the D3 precedence-ordered scanner (typed refs > URLs > file paths > origin-scoped bare tokens) reusing scan_artifact_refs, iter_file_path_matches, and HintContentBudget (promoted _HTTP_URL_PATTERN and _matches_outside_artifact_refs to public names in _file_path_hints.py for cross-file reuse). Added tests/pager/test_link_scan.py and boundary/property tests in tests/ace/tui/test_jump_to_entry_hints.py (sizes 0-250, boundaries at 51/52/53/103/154/205, prefix-freeness, stability, normalize_jump_key round-trip). Verified: ruff check + format, mypy (whole repo, 0 issues), symvision (clean, no epic-symbol whitelist needed), tools/check_feature_flags (clean), and the full local test suite (just test-scoped) shows zero new failures versus a clean stash of the same tree — the 7 failing tests + 1 collection error are pre-existing, unrelated repo drift (recorded as a PROPOSED FOLLOW-UP note). just check's SASE-validation step also fails on that same pre-existing drift before it reaches the test stage, independently of this change.

## Dependencies

- **Blocks:** [sase-uk.2](sase-uk.2.md) ✓ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-uk.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-uk.1/README.md) | [sase-uk.1](sase-uk.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e877263`](https://github.com/sase-org/sase/commit/e877263b65463ef942317df70ab94ba3f168a87c) | feat(pager): add prefix-free jump-hint allocator and link scanner | [sase-uk.1](sase-uk.1.md) | 2026-08-26 18:30:41 EDT |
