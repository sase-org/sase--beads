# Bead: sase-p2.1 — Repo mention catalog

[Bead Pages](../README.md) / [sase-p2](README.md) / sase-p2.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.059](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.059.md) · **Assignee:** `sase-p2.1` · **Size:** medium
**Created:** 2026-08-17 18:09:16 EDT · **Closed:** 2026-08-17 18:58:31 EDT
**Plan:** [202608/prompt\_repo\_mentions.md](https://github.com/sase-org/sase--plans/blob/main/202608/prompt_repo_mentions.md)

## Description

catalog: build the project-scoped repo mention catalog — identifier selection rules, the Rust-compiled matcher, the exact-identifier and path-adjacency span filters, and config declaration ranges.

## Notes

[2026-08-17T22:58:09Z · sase-p2.1] PROPOSED FOLLOW-UP: tests/completion/test_install_zsh.py::test_real_zsh_zcompile_and_registration failed once under the full parallel just check run (32553 passed, 1 failed) but passes reliably standalone — looks like flakiness under parallel/xdist load rather than a real regression; this phase touched only glossary_catalog.py and the new repo_mention_catalog module, unrelated to zsh completion install.

[2026-08-17T22:58:31Z · sase-p2.1] Added src/sase/xprompt/repo_mention_catalog.py (EditorRepoMentionCatalog/Result, RepoMention, RepoMentionSpan, editor_repo_mention_catalog_for_project, scan_repo_mentions, lookup_repo_mention) with 12 passing unit tests covering linked/sidecar/external identifier admission, glossary-name exclusion, exact-identifier + path-adjacency span filters, and config declaration-range resolution. Promoted glossary_catalog's _EditorGlossaryProject/_enabled_project_records/_select_project to public (EditorGlossaryProject/enabled_project_records/select_project) for reuse, updating 5 existing test files accordingly. Added --epic-symbol entries in Justfile for symbols consumed by later phases sase-p2.2/sase-p2.3. Verified: ruff, mypy, and symvision clean on touched files; just check ran full lint gates (all green) plus the full test suite (32553 passed, 13 skipped, 1 unrelated flaky failure in tests/completion/test_install_zsh.py that passes standalone — noted as PROPOSED FOLLOW-UP).

## Dependencies

- **Blocks:** [sase-p2.2](sase-p2.2.md) ✓ · ⧖ 2026-08-17

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-p2.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-p2.1/README.md) | [sase-p2.1](sase-p2.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fb16cfa`](https://github.com/sase-org/sase/commit/fb16cfaf85fdcc9a29ba9ba64c89f6344d7e3d2e) | feat(xprompt): add project-scoped repo mention catalog | [sase-p2.1](sase-p2.1.md) | 2026-08-17 18:59:46 EDT |
