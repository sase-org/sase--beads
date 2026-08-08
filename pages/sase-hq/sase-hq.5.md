# Bead: sase-hq.5 — Add glossary semantics to the xprompt LSP

[Bead Pages](../README.md) / [sase-hq](README.md) / sase-hq.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.w2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.w2/README.md) · **Assignee:** `sase-hq.5` · **Size:** medium
**Created:** 2026-08-08 17:05:12 EDT · **Closed:** 2026-08-08 19:30:23 EDT
**Plan:** [202608/project\_glossary.md](https://github.com/sase-org/sase--plans/blob/main/202608/project_glossary.md)

## Description

lsp: expose project glossary aliases through semantic tokens, hover, and go-to-definition with live cache invalidation.

## Notes

[2026-08-08T23:30:23Z · sase-hq.5] Implemented glossary-aware xprompt LSP semantics in sase-core and verified cargo fmt --check, cargo clippy -p sase_core -p sase_xprompt_lsp --all-targets -- -D warnings, cargo test -p sase_core glossary --quiet, cargo test -p sase_xprompt_lsp --quiet, and git diff --check.

[2026-08-08T23:33:01Z · sase-hq.5] Verified cargo fmt --check; cargo clippy -p sase_core -p sase_xprompt_lsp --all-targets -- -D warnings; cargo test -p sase_core glossary --quiet; cargo test -p sase_xprompt_lsp --quiet; git diff --check

[2026-08-08T23:35:58Z · sase-hq.5] Verified finalizer state before committing agents prompt archive changes; prior checks passed: cargo fmt --check, cargo clippy -p sase_core -p sase_xprompt_lsp --all-targets -- -D warnings, cargo test -p sase_core glossary --quiet, cargo test -p sase_xprompt_lsp --quiet, git diff --check.

## Dependencies

- **Depends on:** [sase-hq.3](sase-hq.3.md) ✓ · ⧖ 2026-08-08
- **Blocks:** [sase-hq.6](sase-hq.6.md) ◐ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hq.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hq.5/README.md) | [sase-hq.5](sase-hq.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--agents | [`sase--agents@cc902eb`](https://github.com/sase-org/sase--agents/commit/cc902ebae2d4ba9d607f885ecab20d816d0c6321) | chore(agents): archive prompt for bbugyi200.athena.sase-hq.5 | [sase-hq.5](sase-hq.5.md) | 2026-08-08 19:37:58 EDT |
