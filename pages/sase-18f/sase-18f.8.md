# Bead: sase-18f.8 — Cache sase-xprompt-lsp builds and dedupe concurrent core builds

[Bead Pages](../README.md) / [sase-18f](README.md) / sase-18f.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0rh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0rh.md) · **Assignee:** `sase-18f.8` · **Size:** medium
**Created:** 2026-09-24 17:19:02 EDT · **Closed:** 2026-09-24 20:01:18 EDT
**Plan:** [202609/green\_just\_check.md](https://github.com/sase-org/sase--plans/blob/main/202609/green_just_check.md)

## Description

lsp-build-cache: add a host-wide content-addressed cache for the sase-xprompt-lsp binary, keyed like the sase_core_rs wheel cache, and use it in rust-lsp-install. Add a per-identity build lock so concurrent workspaces build each new sase-core source identity once.

## Notes

[2026-09-25T00:01:18Z · sase-18f.8--2] Implemented host-wide content-addressed sase-xprompt-lsp cache with profile/toolchain identity and per-identity build locking; rust-lsp-install now uses cache lookup/store. Verified: .venv/bin/pytest -q tests/test_sase_core_wheel_cache_tool.py tests/test_justfile_lint.py (64 passed), git diff --check, and recorded sase tool run check reached passing format/keep-sorted/ruff but stopped at 15 unrelated pre-existing mypy errors in ACE detail/command-line modules.

## Dependencies

- **Blocks:** [sase-18f.9](sase-18f.9.md) ✓ · ⧖ 2026-09-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-18f.8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-18f.8.md) | [sase-18f.8](sase-18f.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`adebe40`](https://github.com/sase-org/sase/commit/adebe400d76371385f420710df6608ec219e8aab) | feat(cache): cache xprompt lsp build artifacts | [sase-18f.8](sase-18f.8.md) | 2026-09-24 20:02:37 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-18f.land][1] | Need the child scope and notes | 2 |
| read-by | [agent:sase-18i.2][2] | Need determine whether the unchanged sase_core_wheel_cache mypy failure is already tracked before noting assigned phase | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18f.land/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-18i.2/README.md

<!-- sase:referenced-by:end -->
