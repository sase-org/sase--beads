# Bead: sase-xz.1 — Shared source-language policy and Python binding

[Bead Pages](../README.md) / [sase-xz](README.md) / sase-xz.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03g](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03g.md) · **Assignee:** `sase-xz.1` · **Size:** medium
**Created:** 2026-09-07 10:51:41 EDT · **Closed:** 2026-09-07 11:44:54 EDT
**Plan:** [202609/pager\_filetype\_syntax.md](https://github.com/sase-org/sase--plans/blob/main/202609/pager_filetype_syntax.md)

## Description

language_contract: implement deterministic language selection, filename provenance, the additive Rust wire/API, and its thin Python facade with binding coverage. Do not activate rendering.

## Notes

[2026-09-07T15:44:54Z · sase-xz.1] Implemented the additive Rust source-language contract (filename mapping, trusted categories, extensionless shebang, stdin-only bounded diff sniff, logical filename precedence) plus PyO3 bindings and a thin Python facade with no producer activation. Verified: sase-core fmt/clippy and workspace tests including source_language unit tests and source_language_bindings_round_trip_wire_payloads; SASE just check (lint including symvision, scoped tests escalated for core-identity/justfile); facade tests against the rebuilt binding (mapping table, shebang, positive/negative diffs, 8KiB bound, provenance precedence); missing/stale sase_core_rs raises ImportError/AttributeError instead of unknown language. Epic-symbols for this phase: none (unused public facade symbols are keyed to sase-xz.4).

## Dependencies

- **Blocks:** [sase-xz.3](sase-xz.3.md) ✓ · ⧖ 2026-09-07
- **Blocks:** [sase-xz.4](sase-xz.4.md) ✓ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xz.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xz.1/README.md) | [sase-xz.1](sase-xz.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7ca1654`](https://github.com/sase-org/sase/commit/7ca1654a2175b3e042b862f9bacb20f04535d2bc) | feat(pager): add source-language facade over the rust contract | [sase-xz.1](sase-xz.1.md) | 2026-09-07 12:37:22 EDT |
| sase-core | [`sase-core@eacd178`](https://github.com/sase-org/sase-core/commit/eacd17823834d441f205289b0c4f30510918734f) | feat(source-language): add pager language policy and wire API | [sase-xz.1](sase-xz.1.md) | 2026-09-07 12:42:24 EDT |
