# Bead: sase-a8.1 — Rust core bead-store path recognition

[Bead Pages](../README.md) / [sase-a8](README.md) / sase-a8.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a8.1` · **Size:** small
**Created:** 2026-07-27 19:46:16 UTC · **Closed:** 2026-07-27 20:02:52 UTC
**Plan:** [202607/beads\_sidecar\_repo.md](https://github.com/sase-org/sase--plans/blob/main/202607/beads_sidecar_repo.md)

## Description

core: teach sase_core's bead-store path heuristics about the `sase/repos/beads` sidecar root so design/plan reference resolution keeps working once bead state leaves the plans repo.

## Notes

[2026-07-27T20:02:17Z · sase-a8.1] Implemented in the sase-core linked repo (crates/sase_core/src/bead/cli.rs). Added the ["beads","repos","sase"] arm to both design_plan_roots (-> beads_dir.parent()/plans) and design_storage_root (-> beads_dir.ancestors().nth(3)), checked before the existing ["beads","plans","repos","sase"] sidecar arm so it cannot be shadowed; the bead-in-plans arm is unchanged. Verified init_store tolerates beads_dirname=="." (Path::components() normalizes the '.' away, so both the shape match and the ancestors indexing stay correct). Tests added: design_plan_roots_resolves_the_beads_sidecar_to_its_plans_sibling, design_storage_root_resolves_the_beads_sidecar_to_the_workspace (each also pins the old sidecar shape), and init_store_writes_a_root_level_store_for_a_dot_dirname. Verified: cargo fmt --all --check clean, cargo clippy -p sase_core --all-targets clean, cargo test -p sase_core all green (975 lib + parity suites). Workspace-wide clippy/test is blocked by an unrelated pre-existing env issue: pyo3 abi3-py312 vs the python 3.11 interpreter in this workspace, affecting sase_core_py only. No files changed in the sase repo, so just check was not applicable. Changes are left uncommitted in the sase-core checkout.

## Dependencies

- **Blocks:** [sase-a8.5](sase-a8.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a8.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a8.1/README.md) | [sase-a8.1](sase-a8.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@2b1f323`](https://github.com/sase-org/sase-core/commit/2b1f323c94ef5be08331064e4acb2e607a657905) | feat(bead): recognize the beads sidecar root in path heuristics (sase-a8.1) | [sase-a8.1](sase-a8.1.md) | 2026-07-27 20:04:03 |
