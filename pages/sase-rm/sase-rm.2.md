# Bead: sase-rm.2 — Unify completion architecture and fast repository catalogs

[Bead Pages](../README.md) / [sase-rm](README.md) / sase-rm.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08u](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08u.md) · **Assignee:** `sase-rm.2` · **Size:** large
**Created:** 2026-08-20 14:47:49 EDT
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

## Dependencies

- **Blocks:** [sase-rm.5](sase-rm.5.md) ◐ · ⧖ 2026-08-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-rm.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rm.2.md) | [sase-rm.2](sase-rm.2.md) | 0 |
