# Bead: sase-ei.1 — Rust bead identity and alias primitive

[Bead Pages](../README.md) / [sase-ei](README.md) / sase-ei.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-eh](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-eh/README.md) · **Assignee:** `sase-ei.1` · **Size:** large
**Created:** 2026-08-03 08:47:58 UTC · **Closed:** 2026-08-03 11:54:30 UTC
**Plan:** [202608/historical\_bead\_reprefix.md](https://github.com/sase-org/sase--plans/blob/main/202608/historical_bead_reprefix.md)

## Description

core-reprefix: add the Rust-backed collision-safe full-store bead ID mapping, canonical event/projection rewrite, persistent old-ID aliases, exact token rewriting, PyO3 bindings, and mixed-prefix lineage tests.

## Notes

[2026-08-03T11:54:30Z · sase-ei.1] Verified linked sase-core with cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace; rebuilt the PyO3 extension with just install; validated installed sase_core_rs bindings; ran focused bead prefix/config/CLI Python tests. Ran just check: lint, Symvision, validation, and committed-plan gates passed; full pytest reached 22985 passed / 7 skipped with no failures before I interrupted an overloaded run after 31:33 while three other workspace full-suite checks were active.

## Dependencies

- **Blocks:** [sase-ei.2](sase-ei.2.md) ◐
- **Blocks:** [sase-ei.3](sase-ei.3.md) ◐
- **Blocks:** [sase-ei.4](sase-ei.4.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ei.1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ei.1.md) | [sase-ei.1](sase-ei.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@0343b6f`](https://github.com/sase-org/sase-core/commit/0343b6f20a8210a631641d8764d8747037c24641) | feat(beads): add prefix migration primitives | [sase-ei.1](sase-ei.1.md) | 2026-08-03 11:56:36 |
| sase | [`b763878`](https://github.com/sase-org/sase/commit/b763878d3dc938672722d6053737f8e706cdc180) | feat(beads): expose prefix migration facade | [sase-ei.1](sase-ei.1.md) | 2026-08-03 11:59:00 |
