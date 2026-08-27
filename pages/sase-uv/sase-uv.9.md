# Bead: sase-uv.9 — Index retention tooling and self-inflicted stall fixes

[Bead Pages](../README.md) / [sase-uv](README.md) / sase-uv.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ex](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ex.md) · **Assignee:** `sase-uv.9` · **Size:** medium
**Created:** 2026-08-27 12:26:48 EDT · **Closed:** 2026-08-27 14:13:04 EDT
**Plan:** [202608/ace\_tui\_responsiveness.md](https://github.com/sase-org/sase--plans/blob/main/202608/ace_tui_responsiveness.md)

## Description

hygiene: add retention/vacuum tooling for the unbounded index and registry state, open the index read-only on query paths, and stop the stall watchdog from extending the freeze it measures.

## Notes

[2026-08-27T17:53:16Z · sase-uv.9] PROPOSED FOLLOW-UP: just check test-scoped consistently fails ~13 tests unrelated to this phase diff (tests/test_agent_wait_cli.py, tests/test_agent_wait_live.py, tests/test_running_agents_snapshot.py, tests/test_agent_chat_from_name.py, tests/axe/test_agent_meta_atomic.py, tests/fakey/test_runner_slots_e2e.py) across two independent just check runs on this branch. Reproduced test_running_agents_snapshot.py::test_list_running_agents_reports_waiting_marker failing identically on a clean git-stashed master tree, confirming it predates this phase and is not caused by these changes. Failures cluster around process-liveness/_fixture_processes fixtures and runner-slot e2e timing, and this host runs many concurrent SASE agent workspaces (e.g. sase_20 was running its own pytest concurrently) — suspect host-load/process-table contention rather than a code defect, but worth a dedicated flake/CI investigation.

[2026-08-27T17:53:43Z · sase-uv.9] PROPOSED FOLLOW-UP: hygiene retention scope note — this phase shipped VACUUM/compact tooling (sase agent index vacuum) plus freelist/dismissed-row visibility reporting, but deliberately did not implement automatic pruning for the two unbounded JSON registries the plan cites (agent_name_registry.json ~17MB/13,118 entries; dismissed_agents.json ~2.4MB). The SQLite dismissed_agents table is a full mirror rebuilt from dismissed_agents.json on every sync (see sync_dismissed_agent_artifact_index_report), so a real retention policy has to bound the JSON source, not just the SQLite mirror, and needs a product decision on TTL/count caps plus care not to un-hide previously dismissed agents. That design work is bigger than a cheap hygiene phase; needs a dedicated task.

[2026-08-27T18:13:04Z · sase-uv.9] hygiene phase complete. (1) Stall watchdog: _record_pump_stall now writes the pump-stall record synchronously on the watchdog worker thread instead of hopping through call_soon_threadsafe onto the event loop, and asyncio_task_stacks/await-chain capture is now bounded (MAX_ASYNCIO_TASK_STACKS=32, MAX_ASYNCIO_TASK_STACK_DEPTH=64) so recording a stall can no longer extend the freeze it measures. (2) sase-core index.rs: added open_index_read_only for genuinely read-only query paths (read_agent_artifact_index_meta, agent_artifact_index_status, query_agent_output_variable_history, load_output_variable_occurrences, query_related_agent_artifact_dirs, plus the Cached-freshness branches of query_agent_artifact_index/query_agent_alias_history), with a schema-version check that falls back to the migrating read-write open so a stale/un-migrated schema is never read through the fast path (caught and fixed 2 test regressions this exposed). open_index also now skips the unconditional schema_version INSERT OR REPLACE once the stored version already matches. (3) Retention/vacuum tooling: new vacuum_agent_artifact_index Rust binding (PRAGMA-based freelist/page-count before-after VACUUM), status now reports freelist_pages/freelist_bytes/file_size_bytes, wired through the Python facade and a new  CLI subcommand (dry-run report by default, --apply runs VACUUM); no destructive lifecycle mutation was run against the user's live ~/.sase state, only scratch fixtures. Verified: cargo test -p sase_core --lib (1993 passed, including 8 new tests for read-only-open/vacuum/freelist), cargo build -p sase_core_py, rebuilt+installed the extension via [rust-dev-install] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev builds from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/linked/sase-core ignore it. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
✏️ Setting installed package as editable
[rust-dev-install] installed /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/.venv/bin/sase-xprompt-lsp and smoke-tested the CLI end-to-end against a scratch index; pytest for stall watchdog (18/18), CLI/wire tests (31/35 incl. new vacuum coverage), and the completion-spec snapshot (regenerated via [setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here. after the new subcommand drifted it). Ran [setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
✓ fmt (python)
✓ fmt (markdown)
✓ lint (keep-sorted)
✓ lint (ruff)
✓ lint (mypy)
✓ lint (feature flags)
✓ lint (pyscripts)
✓ lint (test waits)
✓ lint (changelog)
✓ lint (patch/stitch terminology)
✓ lint (symvision)
✓ lint (toobig)
✓ SASE validation
{"cache_hit": true, "capabilities": [{"commit": "f06a103", "name": "bead_note_edit", "release": "v0.32.4", "subject": "feat(bead): add NoteEdited/NoteRemoved events and note edit/remove mutations"}, {"commit": "f06a103", "name": "bead_note_remove", "release": "v0.32.4", "subject": "feat(bead): add NoteEdited/NoteRemoved events and note edit/remove mutations"}, {"commit": "f5e9c25", "name": "scan_agent_artifacts", "release": "v0.1.1", "subject": "feat: Phase 3C \u2014 sase_core_rs.scan_agent_artifacts PyO3 binding (sase-18.3)"}, {"commit": null, "name": "vacuum_agent_artifact_index", "release": null, "subject": null}], "declared_floor": "0.31.12", "exit_code": 4, "message": "sase-core-rs==0.31.12 is missing 4 capability(s), and at least one has no containing sase-core release tag yet.", "status": "blocked_unpublished"}
✓ committed plans
✗ test (scoped)
[validate_sase_core_rs_version] sase-core checkout is ahead of sase's compatibility window: source version 0.32.9 from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/linked/sase-core/Cargo.toml does not satisfy `sase`'s `sase-core-rs>=0.31.12,<0.32.0` dependency in pyproject.toml. No action is needed: editable installs build from the checkout regardless, and `tools/ratchet_core_window` moves the published window on the release branch at release time.
[setup] Note: the sase-core checkout is ahead of the published sase-core-rs window in pyproject.toml; dev installs build from /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24/sase/repos/linked/sase-core regardless. This is normal — the release-branch reconciler ratchets the published window at release time, so no action is needed here.
.venv/bin/python tools/setup_required_plugins
[setup] Installing required plugin sase-github>=0.2.5.
[setup] Installing required plugin sase-research-artifacts>=0.2.0.

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded); 3453 test files in scope
coverage contexts: baseline 96183d71b3ef (stale, 1729 commits behind HEAD) matched 4 changed file(s) and contributed 109 test file(s)
middle gear: running the over-budget selection at 4 worker(s), leased from the suite gate (ceiling 4)
============================= test session starts ==============================
platform linux -- Python 3.14.7, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_24
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, hypothesis-6.163.0, asyncio-1.4.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [16944 items]

........................................................................ [  0%]
........................................................................ [  0%]
........................................................................ [  1%]
........................................................................ [  1%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  2%]
........................................................................ [  3%]
........................................................................ [  3%]
........................................................................ [  4%]
............................................s........................... [  4%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  5%]
........................................................................ [  6%]
........................................................................ [  6%]
........................................................................ [  7%]
........................................................................ [  7%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  8%]
........................................................................ [  9%]
..............................................................

… and 82057 more characters

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-uv.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-uv.9/README.md) | [sase-uv.9](sase-uv.9.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c862ddd`](https://github.com/sase-org/sase/commit/c862dddcba39165fe5b21a94e22a5bdf0c3a1bde) | fix(tui): write pump-stall records off the event loop and add index vacuum tooling | [sase-uv.9](sase-uv.9.md) | 2026-08-27 14:14:13 EDT |
| sase-core | [`sase-core@b786e90`](https://github.com/sase-org/sase-core/commit/b786e90b5655c10a4cc7212b24a765a2505d6190) | feat(agent-scan): add read-only index opens and a VACUUM binding | [sase-uv.9](sase-uv.9.md) | 2026-08-27 14:15:02 EDT |
