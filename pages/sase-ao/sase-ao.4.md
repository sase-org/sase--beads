# Bead: sase-ao.4 — Surface the alias detail through the xprompt LSP

[Bead Pages](../README.md) / [sase-ao](README.md) / sase-ao.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ao.4` · **Size:** medium
**Created:** 2026-07-29 11:46:34 UTC · **Closed:** 2026-07-29 12:21:18 UTC
**Plan:** [202607/model\_alias\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202607/model_alias_completion.md)

## Description

lsp: consume the new catalog fields in sase-core's xprompt LSP so editors show alias kind, resolution target, provenance, and description, with stable model-before-alias ordering.

## Notes

[2026-07-29T12:21:18Z · sase-ao.4] Implemented additive schema-v1 alias metadata loading and %model LSP presentation with resolved target detail, provenance/config/bucket/pool markdown, alias badges/item kinds, stable model-before-alias sort groups, stale-v1 fallback, and a leading-@ grammar regression. Verified cargo fmt --check; cargo clippy --workspace --all-targets -- -D warnings; cargo test -p sase_core -p sase_xprompt_lsp (990 core tests, 72 LSP unit tests, 6 stdio tests, plus parity/doc tests); and just test-visual (367 passed, 1 skipped). just check passed formatting, Ruff, mypy, pyscripts, Symvision, and size lint before unrelated validation failures for generated-skill drift and the epic plan's missing reciprocal prompt link.

## Dependencies

- **Depends on:** [sase-ao.2](sase-ao.2.md) ✓
- **Blocks:** [sase-ao.5](sase-ao.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| bbugyi200.athena.sase-ao.4 | [sase-ao.4](sase-ao.4.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`89420be`](https://github.com/sase-org/sase-core/commit/89420be1a3e2c02a68dbdc49d7384bf014ba8b3f) | feat(lsp): enrich model alias completions | [sase-ao.4](sase-ao.4.md) | 2026-07-29 12:22:29 |
