# Bead: sase-rm.2 — Unify completion architecture and fast repository catalogs

[Bead Pages](../README.md) / [sase-rm](README.md) / sase-rm.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08u.md) · **Assignee:** `sase-rm.2` · **Size:** large
**Created:** 2026-08-20 14:47:49 EDT · **Closed:** 2026-08-21 05:47:30 EDT
**Plan:** [202608/task\_backlog\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_backlog_closeout.md)

## Description

completion_architecture: move shared model filtering to core, remove eager facade imports, expose the full repository inventory, and add live snippet-trigger completion without violating fast-path budgets.

## Notes

[2026-08-20T20:30:34Z · sase-rm.2] EVIDENCE sase-m1: Shared `%model` filtering now lives in sase-core.

Implementation:
- `crates/sase_core/src/model_completion.rs` — `ModelCompletionEntryWire` plus `filter_model_completion_entries` (leading-`@` alias gate, first-slash provider scope, nested-slash prefix fallback)
- `crates/sase_xprompt_lsp/src/server.rs` — parses catalog rows into the core wire, calls the shared filter, keeps LSP detail/docs/filter_text rendering
- `crates/sase_core_py/src/lib.rs` — `filter_model_completion_entries` binding
- `src/sase/xprompt/model_completion.py` — catalog builder unchanged; filter is a thin `sase_core_rs` adapter with entry/wire round-trip

Checks: `just check` in sase-core (fmt, clippy, workspace tests including 13 `model_completion` unit tests and 11 LSP model tests); primary `tests/test_xprompt_model_completion_filtering.py` plus ACE `test_directive_arg_completion.py -k model_completion`.

[2026-08-20T20:31:23Z · sase-rm.2] EVIDENCE sase-ou: Package facades are lazy and completion-safe.

Implementation:
- `src/sase/_lazy_exports.py` — PEP 562 `__getattr__`/`__dir__` helper
- `src/sase/core/__init__.py`, `src/sase/sdd/__init__.py`, `src/sase/workspace_provider/__init__.py` — deterministic lazy export maps plus TYPE_CHECKING imports so mypy/symvision still see public re-exports
- `src/sase/ace/tui/modals/__init__.py` — TYPE_CHECKING imports for `SnippetsPane*` so the closed `sase-ri.4` `--epic-symbol` entries could be removed from the Justfile
- `tests/test_lazy_package_exports.py` — subprocess import-contract tests for leaves, legacy symbols, and full `__all__`

Checks: `tests/test_lazy_package_exports.py`; `just _lint-symvision`; mypy; import-set assertion in `tests/main/test_completion_candidates_contract.py`.

[2026-08-20T20:31:39Z · sase-rm.2] EVIDENCE sase-ov: Repository completion serves the full inventory.

Implementation:
- `src/sase/completion/candidates/catalog_projects.py` — `repo_candidates` calls `collect_repo_inventory()` after facade imports are lazy; insertion is `repo_display_name`, description is `{kind} · {project display name}`, order preserved, optional project scoping
- `tests/completion/test_candidates_providers.py` — primary, linked, sidecar, external, dedupe, project scoping

Manual: `sase completion candidates repo` lists primary/sidecar/linked rows with kind descriptions (e.g. `sase-core	linked · actstat`).
Checks: repo candidate tests plus the `repo` latency lane in `tests/main/test_completion_candidates_contract.py` (budget tightened to 80ms local / 3x CI).

[2026-08-20T20:31:57Z · sase-rm.2] EVIDENCE sase-re: Live snippet-trigger completion for show/delete.

Implementation:
- `crates/sase_core_py/src/lib.rs` — `load_editor_snippet_catalog(project=None, root_dir=None)` binding
- `src/sase/completion/kinds.py` — `ValueKind.SNIPPET` on `snippet show`/`snippet delete` trigger positionals only
- `src/sase/completion/candidates/catalog_prompts.py` — lazy provider projecting Rust catalog triggers (including generated aliases); catalog env is applied only for the load call
- `docs/completion.md`, `docs/cli.md`, `tests/completion/snapshots/cli_spec.json`

Manual: `sase completion candidates snippet` returns effective triggers; cli_spec attaches kind `snippet` only to show/delete.
Checks: snippet candidate tests (projection, native CWD/overrides, cache refresh, prefix); `snippet` latency lane; parser/spec tests in `tests/completion/test_kinds.py` and `test_build.py`.

[2026-08-20T20:32:14Z · sase-rm.2] PROPOSED FOLLOW-UP: Ratchet the published sase-core-rs floor after this sase-core change is released. `just check` core-floor-probe reports `blocked_unpublished` for `filter_model_completion_entries` and `load_editor_snippet_catalog` against sase-core-rs==0.29.5. Dev installs build from the linked checkout; land should publish sase-core then bump `pyproject.toml`.

PROPOSED FOLLOW-UP: `tests/test_suite_gate_reclaim.py::test_fresh_heartbeat_is_not_reclaimed` failed once during an escalated full-suite run with a worker-token timeout (`Timed out waiting for a SASE pytest worker-token grant`). A later isolated run of unrelated tests passed; treat as gate contention, not a product regression from this phase.

[2026-08-21T09:45:24Z · sase-rm.2] RECOVERY EVIDENCE UPDATE (2026-08-21) for sase-m1 / sase-ou / sase-ov / sase-re:

Implemented in this recovery pass:
- sase-m1: `%model` filtering now has a shared Rust core implementation in `crates/sase_core/src/model_completion.rs`, a strict PyO3 `filter_model_completion_entries` bridge, Python wire serialization in `src/sase/xprompt/model_completion.py`, and LSP routing through `filter_model_completion_candidates` while preserving LSP detail/docs/filter_text rendering.
- sase-ou: `sase.core`, `sase.sdd`, and `sase.workspace_provider` package facades now use the shared PEP 562 helper `src/sase/_lazy_exports.py` with explicit symbol-to-leaf maps, TYPE_CHECKING imports, `dir()` support, and cached attributes; subprocess import-contract coverage is in `tests/test_lazy_facades.py`.
- sase-ov: repo completion now projects `collect_repo_inventory().records` through `repo_display_name(record)` and `{kind} · {project}` descriptions, preserving deterministic dedupe and project scoping without materializing repos. Manual probe: `sase completion candidates repo -p sase` lists primary, sidecar, linked, and external rows.
- sase-re: `sase_core_rs.load_editor_snippet_catalog(project=None, root_dir=None)` exposes the Rust snippet catalog, and `ValueKind.SNIPPET` is attached only to `sase snippet show/delete` trigger positionals. `src/sase/completion/candidates/catalog_snippets.py` provides the lazy fast-path projection and degrades malformed/native errors to no candidates. Manual probe: `sase completion candidates snippet` returns effective triggers and generated aliases.

Generated/docs updated: `tests/completion/snapshots/cli_spec.json` adds shipped kind `snippet` and marks only show/delete trigger positionals; `docs/completion.md` documents repo inventory and snippet trigger sources.

Verification completed:
- `just install` rebuilt/installed the linked `sase_core_rs` bridge.
- Linked core: `cargo fmt --check`; `cargo test -p sase_core model_completion --lib`; `cargo test -p sase_core_py filter_model_completion_entries_binding --lib`; `cargo test -p sase_core_py load_editor_snippet_catalog_binding --lib`; `cargo test -p sase_xprompt_lsp leading_at_filters_model_completion_to_aliases --lib`; full linked-core `just check` passed.
- Primary focused suite: `.venv/bin/pytest tests/test_xprompt_model_completion_filtering.py tests/test_xprompt_model_completion_payload.py tests/completion/test_candidates_providers.py tests/completion/test_kinds.py tests/test_lazy_facades.py tests/main/test_completion_candidates_contract.py tests/completion/test_snapshot.py` passed (71 tests).

Not closed: primary `just check` is blocked by an unrelated pre-existing feature-flag lifecycle failure: rule 7 reports closed flag bead `sase-rk` still has surviving definition `admin_center_config_hub`. That cleanup is broader than this completion recovery and should not be folded into this phase without explicit direction.

[2026-08-21T09:47:30Z · sase-rm.2] Implemented completion architecture recovery: Rust shared %model filtering bridged to Python/LSP, lazy facades, inventory-backed repo completions, Rust snippet completions, docs/snapshot/tests updated. Verified linked sase-core just check passed; primary focused Python suite passed; primary just check still failed on unrelated stale closed flag bead sase-rk/admin_center_config_hub.

## Dependencies

- **Blocks:** [sase-rm.5](sase-rm.5.md) ◐ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rm.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rm.2.md) | [sase-rm.2](sase-rm.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4a3e691`](https://github.com/sase-org/sase/commit/4a3e691964b6715a8698cce29fd5a16d55d50acc) | feat(completion): add inventory and snippet candidate providers | [sase-rm.2](sase-rm.2.md) | 2026-08-21 05:48:40 EDT |
| sase-core | [`sase-core@427d57e`](https://github.com/sase-org/sase-core/commit/427d57e743d02eafbd39388bdba0a35d1966c370) | feat(completion): share model filtering with bindings and LSP | [sase-rm.2](sase-rm.2.md) | 2026-08-21 05:50:41 EDT |
