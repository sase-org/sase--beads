# Bead: sase-s0.1 — Shared finalizer completion and LSP contract

[Bead Pages](../README.md) / [sase-s0](README.md) / sase-s0.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-rr.land.w1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-rr.land.w1.md) · **Assignee:** `sase-s0.1` · **Size:** medium
**Created:** 2026-08-21 20:34:58 UTC · **Closed:** 2026-08-21 20:56:36 UTC
**Plan:** [202608/final\_directive\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/final_directive_completion.md)

## Description

core_completion_contract: add the typed host catalog, selector-aware core candidates, and LSP presentation while keeping the directive hidden.

## Notes

[2026-08-21T20:56:36Z · sase-s0.1] Phase 1 core contract is in sase-core: versioned finalizer-catalog helper wire (request/response + additive instance metadata), independently cached LSP catalog with timeout/stale/warn-once/config-watch invalidation (fetched only for %final argument contexts), selector-aware candidate builder (required/default/optional order, ! removal labels, required omitted from remove, none omitted when required exists, clause-local UTF-16 edits, case-insensitive prefix), dedicated LSP conversion (kinds, sortText, labelDetails, markdown docs, colon/parenthesized snippets kept hidden). Hidden-name guards remain. sase-core just check (fmt, clippy, workspace tests) passed.

## Dependencies

- **Blocks:** [sase-s0.2](sase-s0.2.md) ✓ · ⧖ 2026-08-21
- **Blocks:** [sase-s0.3](sase-s0.3.md) ◐ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s0.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s0.1/README.md) | [sase-s0.1](sase-s0.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@0ec9bbe`](https://github.com/sase-org/sase-core/commit/0ec9bbe6b74024c454953d0deb7d4ebd5410cecf) | feat(editor): add finalizer catalog completion and LSP contract | [sase-s0.1](sase-s0.1.md) | 2026-08-21 20:57:47 UTC |
