# Bead: sase-mf.1 — Define shared size and epic-land model routing primitives

[Bead Pages](../README.md) / [sase-mf](README.md) / sase-mf.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.02n](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.02n.md) · **Assignee:** `sase-mf.1` · **Size:** medium
**Created:** 2026-08-15 14:29:28 EDT · **Closed:** 2026-08-15 14:49:54 EDT
**Plan:** [202608/simplify\_models.md](https://github.com/sase-org/sase--plans/blob/main/202608/simplify_models.md)

## Description

core_model_routes: add and bind the provider-agnostic Rust contract for size alias selection and explicit/configured epic-land model precedence.

## Notes

[2026-08-15T18:49:54Z · sase-mf.1] Added sase_core::model_route and PyO3 bindings size_model_route/select_epic_land_model. Verified all five PhaseSizeWire values map to @<size>, explicit epic-land models win, count>=threshold selects the configured big target otherwise the normal target, invalid sizes (including retired *_worker/epic_lander names), negative counts, non-positive thresholds, booleans, empty targets, and control characters are rejected at the binding, historical agent_scan large_worker/medium_worker fixtures were left unchanged, and linked sase-core just check (fmt, clippy -D warnings, cargo test --workspace) passed.

[2026-08-15T18:51:58Z · sase-mf.1] Linked sase-core just check passed: rustfmt, clippy -D warnings, and cargo test --workspace (unit + PyO3 bindings for size_model_route and select_epic_land_model).

## Dependencies

- **Blocks:** [sase-mf.2](sase-mf.2.md) ◐ · ⧖ 2026-08-15

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-mf.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-mf.1/README.md) | [sase-mf.1](sase-mf.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@b360211`](https://github.com/sase-org/sase-core/commit/b3602118b36d65e4462511a72bc90717cc476909) | feat(model\_route): add shared size and epic-land routing primitives | [sase-mf.1](sase-mf.1.md) | 2026-08-15 14:53:30 EDT |
