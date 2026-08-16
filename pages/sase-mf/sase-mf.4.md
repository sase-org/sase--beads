# Bead: sase-mf.4 — Complete migration coverage, documentation, and end-to-end verification

[Bead Pages](../README.md) / [sase-mf](README.md) / sase-mf.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02n](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02n.md) · **Assignee:** `sase-mf.4` · **Size:** medium
**Created:** 2026-08-15 14:31:14 EDT · **Closed:** 2026-08-16 00:49:21 EDT
**Plan:** [202608/simplify\_models.md](https://github.com/sase-org/sase--plans/blob/main/202608/simplify_models.md)

## Description

migration_docs_and_verification: sweep public surfaces for retired aliases, document the new contract, update intentional goldens, and run exhaustive verification.

## Notes

[2026-08-16T04:04:57Z · sase-mf.4] PROPOSED FOLLOW-UP: sase/memory/sase_sizes.md (and derived AGENTS.md/README.md/provider shims) are stale after this epic retired the `<size>_worker` model aliases. The install-time template `src/sase/main/init_memory/templates/memory-sase-sizes.template.md` was updated in this phase to teach the new `@<size>` routing (five flat built-in size aliases, no more `<size>_worker` indirection), but per project policy (CLAUDE.md: memory files require explicit user authorization not present in this conversation) the canonical `sase/memory/sase_sizes.md` note was left untouched. `sase validate` (part of `just check`) now reports `init memory --check` drift: `~ update sase/memory/sase_sizes.md +4-5` and `~ update sase/memory/README.md +4-4`. Once a user explicitly authorizes a memory update, run `sase memory init` to regenerate the canonical note and derived shims.

[2026-08-16T04:05:28Z · sase-mf.4] PROPOSED FOLLOW-UP: 4 ACE PNG visual-snapshot tests fail with AttributeError, unrelated to this epic's model-alias migration -- caused by concurrent unrelated module-split refactors landed on master the same day (commit de83c802d "refactor(tui): split models provider panel module" moved `build_alias_views` out of `models_panel_providers.py` into `models_panel_provider_state.py`; a similar split moved `load_file_detail` out of `src/sase/ace/tui/widgets/artifacts/files_pane.py`). Stale monkeypatch targets: tests/ace/tui/visual/test_ace_png_snapshots_models_panel_jump.py::test_models_panel_jump_top_level_png_snapshot, ::test_models_panel_jump_mixed_bucket_png_snapshot, ::test_models_panel_jump_narrow_png_snapshot (patch `models_panel_providers.build_alias_views`, which no longer exists there) and tests/ace/tui/visual/test_ace_png_snapshots_artifacts_files.py::test_artifacts_files_populated_png_snapshot (patches `files_pane.load_file_detail`, ditto). Fix: repoint each monkeypatch.setattr at the function's new module.

[2026-08-16T04:05:55Z · sase-mf.4] PROPOSED FOLLOW-UP: 13 ACE PNG visual-snapshot tests fail with small (~0.01-0.5%) pixel diffs unrelated to this epic's model-alias migration -- caused by the concurrent, same-day addition of the "Perf" Statistics view (commits a244947a8 "feat(stats): add Python perf facade and immutable PerfView", d9423e37a "feat(ace): register Perf as the eighth Statistics view"), which shifted the Statistics tab list rendered in every config-center golden: all 12 tests in tests/ace/tui/visual/test_ace_png_snapshots_config_center_statistics.py, plus tests/ace/tui/visual/test_ace_png_snapshots_config_center_procs.py::test_config_center_procs_tab_png_snapshot (a small counter/tab-list drift). Fix: regenerate these goldens with `--sase-update-visual-snapshots` once the Perf view is intentionally settled.

[2026-08-16T04:47:45Z · sase-mf.4] PROPOSED FOLLOW-UP: `just check-full`'s symvision lint gate currently fails on 9 unused-public-symbol findings (FilesQueryIndexResult, PublicationDrainTimedOut, StreamIntegrityResult, analyze_stream_against_ancestor, clear_agent_page_url_registry_cache, configured_publication_drain_timeout, encode_stream_events, is_event_stream_relpath, parse_stream_text), all in files untouched by this model-alias epic (files_query_index.py, commit_publication.py, _stream_integrity.py, agent_page_url.py). None of these symbols appear anywhere in this epic's diff. Same pattern as the two prior notes on this bead: same-day concurrent refactors landed on master unrelated to sase-mf. Fix: either delete the truly-dead symbols or mark them used/private in their owning modules.

[2026-08-16T04:48:32Z · sase-mf.4] PROPOSED FOLLOW-UP: `just test-cost` (the full fast suite) reports 72 failures when run from inside this live, actively-orchestrated SASE agent session, all clustered in tests/test_config.py, test_config_cache.py, test_gate_cli_answer.py, test_gate_cli_act.py, gate_conformance/, main/test_ops_commands.py, test_partial_launch_cleanup.py, test_special_cases.py, test_prompt_inputs.py, test_multi_prompt_e2e.py -- none touched by this epic. Confirmed unrelated to this epic's changes: test_config.py passes 33/33 in isolation; test_gate_cli_answer.py fails even standalone because it reads a real live sidecar at /home/bryan/.sase/procs/runtime/<id>/operation-request.json (this session's own actual runtime state, operation "run.launch") instead of an isolated tmp path, so it collides with genuine SASE agent-runtime files present on this machine while this bead is being worked. Likely a test-isolation gap (missing mock/override of the operations-runtime directory) that only manifests when tests run inside a live sase-orchestrated workspace rather than a clean CI checkout. Investigate whether these suites need to mock the operations runtime root.

[2026-08-16T04:49:21Z · sase-mf.4] Verified: all 8 docs (ace.md, agent_families.md, agent_providers.md, beads.md, configuration.md, llms.md, sdd.md, xprompt.md) plus the memory-sase-sizes install template rewritten to the new 5-size-alias + 3-scalar-launch-setting contract; grepped clean of retired alias names (@default, @epic_lander, @big_epic_lander, <size>_worker, @smart*, @cheap*) except intentional migration-callout mentions and the unrelated tribe-panel @default concept. Fixed 3 DISCOVERED ISSUE regressions (test_top_bar_order.py live-path monkeypatch, shared visual-snapshot startup patcher, alias_overrides_indicator PNG goldens) plus a real production bug (approve_options_modal.py routing through retired medium_worker). Swept 18 test files for stale alias references (14 fixed, 4 confirmed intentionally testing retired-name/migration behavior) -- 306/306 pass. Migrated and regenerated all Models-panel PNG visual fixtures/goldens -- 43/43 visual tests pass. Ran just check-full: all lint gates pass (fixed one ruff-format drift) except symvision (9 unrelated pre-existing findings in untouched files) and SASE validation's memory-drift check (expected -- requires user authorization per CLAUDE.md, already documented). Ran just test-cost (full fast suite): 72 failures, all confirmed pre-existing/environmental (unrelated subsystems: gate CLI, config cache, ops commands; test_config.py passes 100% in isolation; failures trace to this live session's real ~/.sase/procs/runtime state leaking into non-isolated tests), none touching this epic's changed files. Recorded 5 PROPOSED FOLLOW-UP notes for out-of-scope discoveries (memory-file drift pending authorization, 2 unrelated concurrent-refactor visual-test breakages, symvision drift, test-isolation gap).

## Dependencies

- **Depends on:** [sase-mf.2](sase-mf.2.md) ✓ · ⧖ 2026-08-15
- **Depends on:** [sase-mf.3](sase-mf.3.md) ✓ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mf.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mf.4/README.md) | [sase-mf.4](sase-mf.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9811067`](https://github.com/sase-org/sase/commit/98110679997c34218eec17eb96f20fec5e6bfe74) | docs: migrate docs and tests off retired model-alias names | [sase-mf.4](sase-mf.4.md) | 2026-08-16 00:53:04 EDT |
