# Bead: sase-ug.3 — Projected edges from facts SASE already owns

[Bead Pages](../README.md) / [sase-ug](README.md) / sase-ug.3

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0eh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0eh.md) · **Assignee:** `sase-ug.3` · **Size:** large
**Created:** 2026-08-26 14:48:25 EDT
**Plan:** [202608/link\_rail\_every\_tab.md](https://github.com/sase-org/sase--plans/blob/main/202608/link_rail_every_tab.md)

## Description

project: add a recomputed projection layer that turns commit trailers, agent metadata, and chop launch identity into typed edges without growing the durable store.

## Notes

[2026-08-26T21:50:37Z · sase-ug.3--1] Final verification of the projected-artifact-link-edges plan, re-measured against the current tree (project `gh_sase-org__sase`).

**`just check-full` (18m budget, ran via monitor):** 37343 passed, 13 skipped, 2 failed, 1 collection error — all three pre-existing and unrelated: `tests/test_contract_manifest.py::test_contract_manifest_matches_marker_selection` (sase-iu family), `tests/memory/test_memory_selector_render.py::test_note_section_retains_children_listing_beneath_its_header` (sase-uh), and the `tests/ace/tui/visual/test_ace_png_snapshots_agents_metadata_search.py` collection ImportError (sase-ue/sase-ui). No failures caused by this work. `just check` (fmt, every lint gate, SASE validation, committed plans, scoped tests) was already green before and after the fix below.

**Re-measured row counts** (was: stitch-agent 5,913 / agent-bead 5,137 / stitch-bead 1,344 / chop-agent 110 / total 12,504 at 452ac54cf): now stitch-agent 5,916, agent-bead 5,147, stitch-bead 1,347, chop-agent 110 (unchanged, as expected — config-derived), total projected 12,520. Growth of +16 rows matches new commits/agents landed since the plan's measurement; nothing unexpected. On-disk aggregate: 13,812 total rows (12,520 projected + 1,292 store-backed), 5.84 MB.

**Verification checklist, run against the live project with this workspace's editable install (`.venv/bin/sase`, not the globally-installed uv-tool `sase` which resolves to a different checkout — worth remembering for any future agent verifying in-place changes here):**

- `sase artifact doctor` completes clean (no errors, "Stale Links tables: none"). Directly invoked `_check_artifact_links_aggregate` twice back to back: `status=OK`, `stale=False`, `rows=13804`, `projected_rows` reported separately in `data` (12,520) rather than folded into the stale-comparison or the "Rows by origin" summary — confirms the check compares store-backed rows only and does not turn red merely because HEAD moved or projected rows were recomputed.
- `sase artifact link list bead:sase-ud.3` and `load_neighborhood_rows("bead:sase-ud.3")` both return zero projected rows even though `agent-bead` projects real edges onto that bead — confirms the per-ref aggregate-fallback filter protects the audited-read footer and the launch-prompt one-hop expansion.
- `remove_rows` refusal for a purely-projected pair: confirmed correct once the pair is materialized on disk (matches existing test coverage in `tests/sdd/test_artifact_link_store_projected.py`). Noted one narrow, harmless edge case: the refusal check reads the on-disk aggregate (`load_aggregate()`), so calling `link rm` on a projected pair in the brief window before any rebuild has ever materialized it is a silent no-op instead of the informative refusal — the next mutating call's `rebuild_aggregate()` closes the window immediately and no data is ever at risk (nothing durable to delete). Not worth a fix; flagging only for awareness.
- `sase agent search 'relation:produced-by'` and `'relation:launched'` parse and execute without an "unknown relation" error (the registry-driven claim the plan verification names), but currently return zero matches: `sase.ace.tui.relations.artifact_links.load_artifact_links_snapshot` (which feeds `agents/cli_search.py`) reads the on-disk aggregate JSON directly rather than through `ArtifactLinkStore.projected_rows()`/`preview_aggregate()`, so a projection-only relation (`written_by: projection`, never store-backed) can't surface there. This matches the plan's own narrower claim ("`relation:produced-by` filtering ... come for free" is about the query enum/registry, not this reader's data flow) and is consistent with the epic's later phases (`--source store|index`, the rail widget) being the ones that widen other readers. Not a regression; just confirming the boundary.

**One real gap found and fixed:** the plan's verification explicitly requires `sase artifact link list --origin projected -l 5` to show projected rows (line 273 of the plan calls this out as "the one deliberate exception: with no reference it reads the aggregate and should show projected rows"). `handle_link_list`'s no-reference branch was calling `store.load_aggregate()` only, which never contains projected rows before the first rebuild — so `--origin projected` returned "No artifact links found" and `--origin manual` happened to still work by accident. Fixed in `src/sase/artifact_cli/link_ops.py` by merging `store.projected_rows()` into the loaded rows via `unique_rows` (same first-wins precedence `project_aggregate_rows` uses, so a store-backed row beats a projected one on identity collision). Added `test_list_without_reference_merges_in_projected_rows` to `tests/main/test_artifact_cli_link.py` covering both `--origin projected` and `--origin manual`. Ran the full `tests/artifact_links/`, `tests/sdd/test_artifact_link_store_projected.py`, and `tests/main/test_artifact_cli_link.py` suites (82 passed) plus `just check` (fmt/lint/SASE-validation/scoped-tests, all green) after this fix; did not re-run the full 18-minute `just check-full` for this small additive, narrowly-tested change given the two-speed verification guidance and the already-green full run moments earlier.

Also closing note for sase-uj: the pre-existing `tests/test_notification_gate_durability.py` missing-pragma lint failure that blocked `just check`/`just check-full` was fixed directly (trivial one-line `sase-test-wait` pragma) as part of landing this phase; sase-uj can close referencing this bead's commit(s).

Plan (sase-ug.3) is implementation-complete, tested, and verified.

## Dependencies

- **Depends on:** [sase-ug.1](sase-ug.1.md) ✓ · ⧖ 2026-08-26
- **Blocks:** [sase-ug.4](sase-ug.4.md) ◐ · ⧖ 2026-08-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ug.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ug.3.md) | [sase-ug.3](sase-ug.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4bce1a4`](https://github.com/sase-org/sase/commit/4bce1a4f68d985c623611416ea8187da7052609f) | feat(artifact-links): project recomputed edges into the read model (sase-ug.3) | [sase-ug.3](sase-ug.3.md) | 2026-08-26 18:45:13 EDT |
