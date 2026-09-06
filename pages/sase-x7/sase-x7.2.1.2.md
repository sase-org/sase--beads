# Bead: sase-x7.2.1.2 — Build the backup and restore engine and the host drain inventory

[Bead Pages](../README.md) / [sase-x7.2.1](sase-x7.2.1.md) / sase-x7.2.1.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-x7.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.2.md) · **Assignee:** `sase-x7.2.1.2` · **Size:** medium
**Created:** 2026-09-05 19:32:04 EDT · **Closed:** 2026-09-05 21:39:05 EDT
**Plan:** [202609/migration\_kit.md](https://github.com/sase-org/sase--plans/blob/main/202609/migration_kit.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:a0fd26f83bdbbb9f851b0216 | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

kit-backup: Introduce the `sase migrate` command group with `backup` and `restore`, implement quiescent, checksummed, SQLite-consistent backups written outside every runtime root, implement staged restore with verification, and produce the missing fleet inventory of installed distributions, entry points, shell completions, timers, and scheduled updaters (census gap G3).

## Notes

[2026-09-06T01:36:25Z · sase-x7.2.1.2] PROPOSED FOLLOW-UP: sase-core-rs v0.32.25 appears to already contain every migration_* binding -- tools/probe_core_floor in this just check run reports "migration_acquire_bounded_lock", "migration_fingerprint", "migration_journal_record_normalize", "migration_manifest_normalize", "migration_plan_next_step", "migration_reconcile_procs", "migration_residue_classify", "migration_tree_digest", and "migration_wire_schema_version" all "first appears in sase-core 1bf6023 ... release v0.32.25 contains it", contradicting sase-x7.2.1.1's note that the latest publish (0.32.24) lacked them. kit-driver (sase-x7.2.1.3) should re-run tools/probe_core_floor before assuming the publish barrier is still blocking, and if confirmed, bump the sase-core-rs floor in pyproject.toml past 0.32.19 and ratchet sase-core-revision.txt (just ratchet-core-revision) rather than re-doing the publish step.

[2026-09-06T01:36:52Z · sase-x7.2.1.2] PROPOSED FOLLOW-UP: discovered pre-existing, order-dependent test failures unrelated to this phase (no files under src/sase/ace or the clan_summary scripts were touched here) -- tests/ace/tui/widgets/test_prompt_panel_section_navigation_targets.py::test_active_section_reconciles_across_same_document_rerender and ::test_cheap_paint_preserves_section_until_enriched_layout_returns fail deterministically together when the file runs with pytest-randomly (AgentPromptPanel.active_section_identity resolves to None instead of "two"), and tests/test_clan_summary_script_execution.py::test_timed_out_summary_script_exits_on_sigterm_without_sigkill failed once under a heavy ~39k-test parallel run but passed 4/4 in isolation (timing-sensitive SIGTERM/SIGKILL margin). File as a CI-failure/flake task bead for the ACE TUI prompt-panel ordering bug and a flake bead for the clan_summary signal-timing test.

[2026-09-06T01:39:05Z · sase-x7.2.1.2] Verified: sase migrate backup/restore CLI group added (src/sase/migration_kit/{paths,hashing,sqlite_backup,manifest,provenance,backup,restore}.py + parser_migrate.py/migrate_handler.py, lazy-imported, not in _COMPACT_ROOT_COMMANDS). Backup engine: SQLite stores copied via sqlite3.Connection.backup() + PRAGMA integrity_check (never raw bytes, so WAL-mode writers can't produce a torn copy), modes/uid/gid/symlinks preserved without dereferencing, free-space refusal at source*1.15, MANIFEST.json/SHA256SUMS/provenance.json written, optional --secondary copy. Restore: SHA256SUMS verified before anything is touched, staged into cutover root, diff + ownership-delta reporting, --apply swaps live root aside (never deleted, kept as .pre-restore-<ts>) and moves the stage into place; backup itself is never mutated. Fixed a real bug found in review: is_contained_backup_root compared already-expanded absolute paths against unexpanded ~-prefixed strings and would have silently reported every real path as contained; now expands both sides and is regression-tested. 44 unit/integration tests + CLI parser tests pass (tests/migration_kit/, tests/main/test_migrate_parser.py) covering WAL consistency under a live writer, symlink/mode preservation, checksum verification, free-space refusal, containment, and staged restore with ownership deltas. Proved end-to-end against real production data: rsynced a 5.7G/244,944-file scratch copy of athena's live ~/.sase (excluding reproducible projects/ and cache/), ran backup --apply (ok, 6/6 live sqlite stores incl. agent_artifact_index.sqlite, chats_catalog.sqlite, dismissed_bundles/index.sqlite, telemetry/metrics.sqlite all integrity_check=ok), spot-verified 20 random checksums by hand, then ran restore dry-run verifying all 244,944 checksums with the expected WAL/SHM-sidecar diff. G3 fleet inventory published and attached (file:explicit:a0fd26f83bdbbb9f851b0216): athena and apollo fully probed (installed distributions/entry points/stale shell completions/timers/cron/the one live drain hazard -- apollo's unattended axe orchestrator); mac unreachable at probe time (best-effort, deferred to kit-rehearsal's reachability window per its own acceptance bar). just check is clean (fmt, ruff, mypy, symvision with zero new whitelist entries -- unused symbols were made private or deleted instead, ratchet-core-revision lint, scoped tests); regenerated the completion snapshot and added the required DirOpReview audit entry for restore's directory swap. sase bead epic-symbols is clean. Recorded two PROPOSED FOLLOW-UP notes: sase-core-rs v0.32.25 may already publish the migration_* bindings sase-x7.2.1.1 found missing, and two pre-existing unrelated test issues discovered incidentally (ACE TUI prompt-panel ordering, clan_summary sigterm timing flake).

## Dependencies

- **Depends on:** [sase-x7.2.1.1](sase-x7.2.1.1.md) ✓ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.2.1.3](sase-x7.2.1.3.md) ✓ · ⧖ 2026-09-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.2.1.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-x7.2.1.2/README.md) | [sase-x7.2.1.2](sase-x7.2.1.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`43164ea`](https://github.com/sase-org/sase/commit/43164eace6ba51bce0ec00065f645e1ab78feac6) | feat(migrate): add sase migrate backup/restore and G3 fleet inventory | [sase-x7.2.1.2](sase-x7.2.1.2.md) | 2026-09-05 21:40:14 EDT |
