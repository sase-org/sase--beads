# Bead: sase-1sb.3 — Path-component validation for repo clone dirs and project log paths

[Bead Pages](../README.md) / [sase-1sb](README.md) / sase-1sb.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1bk](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1bk.md) · **Assignee:** `sase-1sb.3` · **Size:** medium
**Created:** 2026-11-11 17:38:53 EST · **Closed:** 2026-11-11 21:55:31 EST
**Plan:** [202611/security\_bug\_audit\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202611/security_bug_audit_fixes.md)

## Description

Two confirmed containment gaps where repo-resident (hence agent/third-party
writable) strings reach filesystem path joins without the component validation
their sibling helpers already have:

1. src/sase/_linked_repo_paths.py: `linked_repo_clone_dir` (~line 28) and
   `sidecar_repo_clone_dir` (~line 58) do `Path(host_checkout).joinpath(*SUBDIR,
   name)` then `normalize_path()` (which resolves), so a `name`/`dirname` like
   `../../../../home/user/.config/x` escapes `<checkout>/sase/repos/`. The same
   file's `external_repo_clone_dir` (~line 36) and `hidden_sidecar_clone_dir`
   (~line 66) validate components ("must be a safe path component"), proving the
   invariant is intended. Origins: `sase.yml` `repos.sidecar.custom.<role>` keys
   and `repos.linked[].name` (src/sase/_linked_repo_config_entries.py only strips
   empties), and `.sase/sdd-store.json` role keys / `repo` basenames
   (`_repo_basename("x/..") == ".."`, _linked_repo_paths.py ~line 85;
   src/sase/sdd/_store_records.py accepts any non-empty role). Reached with no
   user interaction by sidecar auto-connect/auto-sync
   (src/sase/_sidecar_auto_connect.py, src/sase/_sidecar_auto_sync.py →
   src/sase/workspace_provider/_ownership_paths.py `kind_root_for_context`) and by
   clone/materialize paths (src/sase/_linked_repo_workspaces.py →
   `ensure_git_clone_at` in src/sase/workspace_provider/_utils_checkout_clone.py,
   which has no containment check). Fix: apply the `hidden_sidecar_clone_dir`
   safe-component check (non-empty, not `.`/`..`, no `/`, `\`, NUL, no leading
   `.`, no surrounding whitespace) to `name`/`dirname` in `linked_repo_clone_dir`
   and `sidecar_repo_clone_dir`; reject non-component role keys where config and
   sdd-store records are parsed (`_sidecar_bucket_entries` /
   `_sidecars_from_raw`); and add a belt-and-suspenders containment check in
   `ensure_git_clone_at` (refuse targets not under the expected `sase/repos/`
   root when invoked for linked/sidecar clones).

2. Project-name joins under ~/.sase/projects/: `validate_sase_project_name`
   (src/sase/core/paths.py ~line 175, docstring: rejecting separators/dots "is
   what enforces containment under sase_projects_dir()") is called at somesinks
   (src/sase/_plan_approval_artifacts.py,
   src/sase/agents_sync/prompt_archive/protection.py) but NOT in five log-path
   helpers that mkdir+append at `sase_projects_dir() / project_name / ...`:
   src/sase/artifact_read_log.py `artifact_read_log_path` (~line 54),
   src/sase/memory/_read_log_events.py (~line 160), src/sase/skills/use_log.py
   (~line 130), src/sase/repo_open_log.py (~line 115),
   src/sase/memory/legacy_glossary_read_log.py (~line 56). The name can originate
   from a committed `.sase/checkout.json` `project_name`
   (src/sase/workspace_provider/marker.py `from_dict` accepts any string;
   preferred by `project_memory_name` in src/sase/main/init_memory/config.py) or
   from a git-URL basename, so a hostile checkout makes audited reads mkdir and
   append outside ~/.sase/projects/. Fix: route all five through one shared
   helper that calls `validate_sase_project_name` (decide and document the
   failure behavior: raise, or fall back to a sanitized name — prefer raising to
   match the validated sinks), and additionally validate
   `CheckoutMarker.from_dict`'s `project_name`/`project_key` at parse time.

Tests: traversal attempts (`..`-bearing and absolute names) for each fixed helper
must raise/refuse and must not create directories; valid names keep working.
Check tests/ for existing coverage of these modules and extend it.

## Notes

[2026-11-12T02:55:31Z · sase-1sb.3] Path containment for linked/sidecar clone dirs and project log helpers. Traversal names raise/refuse and do not create directories; valid names still work. Checkout markers validate project_name and slash-separated project_key without rejecting live sase-org/sase keys or empty fallback fields. sase tool run check passed (f059f6d97c5ce06f9c789fbc5b5c6461). No leftover --epic-symbol entries.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sb.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1sb.3/README.md) | [sase-1sb.3](sase-1sb.3.md) | 0 |
