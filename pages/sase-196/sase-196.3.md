# Bead: sase-196.3 — Scope the completion seal to obligated repositories in sase-core

[Bead Pages](../README.md) / [sase-196](README.md) / sase-196.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ry.f0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ry.f0.md) · **Assignee:** `sase-196.3` · **Size:** medium
**Created:** 2026-09-25 09:05:36 EDT · **Closed:** 2026-09-25 10:28:59 EDT
**Plan:** [202609/agents\_sidecar\_orphan\_objects.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_sidecar_orphan_objects.md)

## Description

seal-scope-core: in the sase-core continuation seal and evaluator, apply the protected/foreign, completeness, and unknown-HEAD checks and compute the worktree fingerprint only over repositories that have a repository decision. Errors should name the repository.

## Notes

[2026-09-25T13:47:22Z · sase-196.3] Recording flake follow-up for phase bead PROPOSED FOLLOW-UP: sase-core check hit known flake sase-17n, private_argv test fails full-lane only, passes alone with and without this phase changes -r

[2026-09-25T14:28:59Z · sase-196.3--1] seal-scope-core done: seal checks and worktree fingerprint scoped to repos with a repository decision, protected/foreign errors name repo_id and name (completion.rs, completion_eval.rs). Verified: continuation Rust unit tests pass, sase-core fmt-check/features/clippy pass, 19 Python tests pass (test_final_prepare + monitor host completion), epic-symbols clean, flake sase-17n already noted as follow-up.

## Dependencies

- **Blocks:** [sase-196.4](sase-196.4.md) ◐ · ⧖ 2026-09-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-196.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-196.3.md) | [sase-196.3](sase-196.3.md) | 0 |
