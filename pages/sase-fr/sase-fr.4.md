# Bead: sase-fr.4 — sase bead show, JSON, list badges, and search

[Bead Pages](../README.md) / [sase-fr](README.md) / sase-fr.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tr](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tr/README.md) · **Assignee:** `sase-fr.4` · **Size:** medium
**Created:** 2026-08-05 21:20:12 EDT · **Closed:** 2026-08-05 23:26:49 EDT
**Plan:** [202608/bead\_close\_history.md](https://github.com/sase-org/sase--plans/blob/main/202608/bead_close_history.md)

## Description

cli: render the PREVIOUSLY CLOSED section and the reopening-+1 marker in bead detail, emit close_history in detail JSON, add the reopen badge to list/ready/search rows, and make archived close reasons searchable.

## Notes

[2026-08-06T03:24:42Z · sase-fr.4] PROPOSED FOLLOW-UP: archived close reasons are still not findable by `sase bead search` — the Python `_search_field_value` map now carries a `close_history` entry, but match selection happens in Rust (crates/sase_core/src/bead/search.rs), which has no close_history field, so the field name never appears in matched_fields; this is the same gap sase-fr.1 already recorded and it stays open until that sase-core change ships.

[2026-08-06T03:25:18Z · sase-fr.4] PROPOSED FOLLOW-UP: `just check` flake corroboration for sase-ct — the full parallel run failed tests/ace/tui/test_app_title.py::test_on_mount_refines_title_to_resolved_version and tests/test_contract_manifest.py::test_contract_set_serial_runtime_stays_within_budget while three sibling workspaces ran their own checks; both pass in isolation and neither touches any file this phase changed.

[2026-08-06T03:26:00Z · sase-fr.4] Scope note: the `has:reopened` filter value was added to BEAD_HAS_VALUES in filter_query.py here (the only close-history-relevant surface that module owns — it holds no search haystack); the ACE `has_labels` producer that makes the value match rows belongs to sase-fr.6. Until that lands, `has:reopened` parses and matches nothing rather than erroring.

[2026-08-06T03:26:49Z · sase-fr.4] Rendered close history across every sase bead read surface. cli_detail.py: [↺N] header badge, a PREVIOUSLY CLOSED block placed immediately after RESOLUTION (newest first, absolute times only, Reason prose through _prose_lines at indent 6, '(none)' placeholder when no reason was recorded), and the ↺ reopened-this-task marker on the joining +1 entry. cli_detail_json.py: unconditional close_history in wire field order plus a derived reopened_bead flag on every plus_one_evidence entry. cli_query.py: one shared _row_badges helper now feeds list/ready/blocked/search rows so the two badges cannot drift apart, and close_history_search_text joined the search-field map. filter_query.py: has:reopened accepted. Removed the six now-redundant sase-fr --epic-symbol entries from the Justfile since this phase consumes every reopen_presentation export.

Verified: just lint clean including symvision; just check green apart from two unrelated failures (tests/ace/tui/test_app_title.py and the contract serial-runtime budget) that each pass in isolation and are noted above as sase-ct corroboration. tests/test_bead 1434 passed/1 skipped. New tests/test_bead/test_cli_close_history.py (22 tests) covers record ordering, the closed-then-why-then-reopened narrative, the missing-reason placeholder, section placement above DESCRIPTION and below RESOLUTION for a closed-again bead, both header badges, marker exclusivity (a reporter match with a different timestamp does not mark), JSON shape and unconditional key, all four row surfaces, and the search text. A reopened_task builder joined the show-style CORPUS, so the SGR-strip invariant and every wrap width now exercise the new section, and show_style_reopened_task.ansi pins it byte-for-byte. Regenerated the five *_json.stdout goldens for the new key.

[2026-08-06T03:28:06Z · sase-fr.4] Reopen presentation wired end-to-end: [↺N] header badge, PREVIOUSLY CLOSED section after RESOLUTION, ↺ marker on the joined +1 entry, close_history + reopened_bead in JSON, shared _row_badges across list/ready/blocked/search, close_history_search_text in the search field map, has:reopened filter token, and the six sase-fr --epic-symbol whitelist entries removed from the Justfile. just lint clean (incl. symvision); tests/test_bead 1434 passed / 1 skipped, including a new 22-test tests/test_bead/test_cli_close_history.py and a reopened_task show-style corpus entry pinned by show_style_reopened_task.ansi.

## Dependencies

- **Depends on:** [sase-fr.3](sase-fr.3.md) ✓ · ⧖ 2026-08-05
- **Blocks:** [sase-fr.8](sase-fr.8.md) ✓ · ⧖ 2026-08-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fr.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fr.4/README.md) | [sase-fr.4](sase-fr.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d0e59df`](https://github.com/sase-org/sase/commit/d0e59dfdd4d37de450f997bbc1d418ba4fa8af35) | feat(bead): surface reopen history in bead show, JSON, list rows, and search | [sase-fr.4](sase-fr.4.md) | 2026-08-05 23:29:12 EDT |
