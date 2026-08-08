# Bead: sase-ho.4 — Unify filtered completion across invocation surfaces

[Bead Pages](../README.md) / [sase-ho](README.md) / sase-ho.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.vw](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.vw/README.md) · **Assignee:** `sase-ho.4` · **Size:** medium
**Created:** 2026-08-08 13:33:25 EDT · **Closed:** 2026-08-08 18:02:06 EDT
**Plan:** [202608/artifact\_reference\_xprompts.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_reference_xprompts.md)

## Description

reference-completion: drive TUI and LSP completion for both `@kind:` and `#ref/kind` from the same filtered artifact inventory and invalidate it on all relevant source/config changes.

## Notes

[2026-08-08T22:02:06Z · sase-ho.4] Implemented unified filtered artifact/ref completion across TUI and LSP paths; verified targeted Python completion/prompt-catalog/write-target tests, Rust LSP ref/invalidation tests, and final just check.

[2026-08-08T22:03:28Z · sase-ho.4] Verified focused Python/Rust tests and final just check passed.

## Dependencies

- **Depends on:** [sase-ho.1](sase-ho.1.md) ✓ · ⧖ 2026-08-08
- **Depends on:** [sase-ho.2](sase-ho.2.md) ✓ · ⧖ 2026-08-08
- **Blocks:** [sase-ho.5](sase-ho.5.md) ◐ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ho.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ho.4/README.md) | [sase-ho.4](sase-ho.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@5764c32`](https://github.com/sase-org/sase-core/commit/5764c323bdc19376de026d2fefa50c12b678a34e) | fix(lsp): invalidate ref completion sources | [sase-ho.4](sase-ho.4.md) | 2026-08-08 18:04:33 EDT |
