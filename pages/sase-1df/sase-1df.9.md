# Bead: sase-1df.9 — TUI and LSP Jinja completion parity suite

[Bead Pages](../README.md) / [sase-1df](README.md) / sase-1df.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3g](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3g.md) · **Assignee:** `sase-1df.9` · **Size:** small
**Created:** 2026-09-30 08:47:33 EDT · **Closed:** 2026-09-30 13:32:55 EDT
**Plan:** [202609/jinja\_variable\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/jinja_variable_completion.md)

## Description

parity: prove the LSP binary and the Python adapter return identical ordered candidates on shared fixtures, including lifted-frontmatter versus inline-frontmatter documents and xprompt-path scope.

## Notes

[2026-09-30T17:32:02Z · sase-1df.9--1] PROPOSED FOLLOW-UP: TUI menu-rows parity pilot waits on the sase-1df.7 engine-backed widget rewrite (current widget still uses jinja_inspect)

[2026-09-30T17:32:55Z · sase-1df.9--1] LSP/adapter Jinja parity green: new tests/test_xprompt_jinja_lsp_parity.py (4 tests: prompt cursors, input-declaring run-name hiding, xprompt skill path, lifted-vs-inline frontmatter) plus tests/test_xprompt_directive_completion_parity.py, 40 passed; ruff check+format clean on changed files; mypy shows only 2 pre-existing errors in untouched harness files (reproduce on unmodified directive test). Fixed 3 test-file expectation bugs (missing cursor markers, wait.->loop. member fixture, missing helper, B905 strict=True); no engine/LSP divergence found.

## Dependencies

- **Depends on:** [sase-1df.5](sase-1df.5.md) ✓ · ⧖ 2026-09-30
- **Depends on:** [sase-1df.6](sase-1df.6.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1df.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1df.9.md) | [sase-1df.9](sase-1df.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9c867a3`](https://github.com/sase-org/sase/commit/9c867a38542226a925e4bda371d2d25ae6b9a8d4) | test(xprompt): LSP/adapter Jinja completion parity suite (sase-1df.9) | [sase-1df.9](sase-1df.9.md) | 2026-09-30 14:23:38 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1df.9--2][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1df.9.md

<!-- sase:referenced-by:end -->
