# Bead: sase-ky.1 — Rename the SDD plan-reference grammar in sase-core

[Bead Pages](../README.md) / [sase-ky](README.md) / sase-ky.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.zl.f1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.zl.f1.md) · **Assignee:** `sase-ky.1` · **Size:** small
**Created:** 2026-08-13 12:21:47 EDT · **Closed:** 2026-08-13 12:32:43 EDT
**Plan:** [plans:202608/plan\_ref\_kind\_rename.md](https://github.com/sase-org/sase--plans/blob/main/202608/plan_ref_kind_rename.md)

## Description

core: rename PLAN_REFERENCE_KIND/PREFIX to plan in crates/sase_core/src/plan/refs.rs, keep `plans:` as a read-only input alias that re-renders canonically, and update the Rust tests and the plan_reference_render kind guard.

## Notes

[2026-08-13T16:32:43Z · sase-ky.1] Verified cargo fmt and full cargo test in sase-core; plan refs now render plan:, plans: parses as a read-only alias, wire schema remains v1, and remaining plans: hits are alias/artifact-ref coverage.

[2026-08-13T16:34:37Z · sase-ky.1] Verified cargo fmt, focused plan refs and Python binding tests, full cargo test, and wire schema remains v1; canonical plan: rendering keeps plans: as a read-only alias.

## Dependencies

- **Blocks:** [sase-ky.2](sase-ky.2.md) ✓ · ⧖ 2026-08-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ky.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ky.1/README.md) | [sase-ky.1](sase-ky.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@f08e5ad`](https://github.com/sase-org/sase-core/commit/f08e5ad0b289bf07c503fe6f848fdc131fdfde89) | feat: canonicalize plan references with plan prefix | [sase-ky.1](sase-ky.1.md) | 2026-08-13 12:35:26 EDT |
